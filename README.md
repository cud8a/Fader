# Fader
Use it like a standard UIImageView. The Image will fade in and fade out forever. Intended to be used as a progress indicator.

    import UIKit

    @IBDesignable
    class FadingImageView: UIImageView {
        required init?(coder aDecoder: NSCoder) {
            super.init(coder: aDecoder)
            startFadingAnimation()
        }
    
        private func startFadingAnimation() {
            let animation : CABasicAnimation = CABasicAnimation(keyPath: "opacity");
        
            animation.fromValue = 1
            animation.toValue = 0
        
            animation.duration = 1.5
            animation.autoreverses = true
            animation.repeatCount = Float.infinity
            animation.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionEaseInEaseOut)
        
            layer.add(animation, forKey: nil)
        }
    }
