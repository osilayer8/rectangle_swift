import UIKit

class DrawExamples: UIView {

    override func drawRect(rect: CGRect) {
        
        // Drawing code
        let radius:CGFloat = 43.0
        
        // Create the circle layer
        let circle = CAShapeLayer()
        
        // Set the center of the circle to be the center of the view
        let center = CGPointMake(CGRectGetMidX(self.frame), CGRectGetMidY(self.frame) - 150)
        
        let fractionOfCircle = 1.0
        
        //let twoPi = 2.0 * Double(M_PI)
        // The starting angle is given by the fraction of the circle that the point is at, divided by 2 * Pi and less
        // We subtract M_PI_2 to rotate the circle 90 degrees to make it more intuitive (i.e. like a clock face with zero at the top, 1/4 at RHS, 1/2 at bottom, etc.)
        //let starter = 2 * Double(M_PI) * Double(radius)
        let startAngle = 1/4 * Double(M_PI) * 70
        //Double(fractionOfCircle) / Double(twoPi) - Double(M_PI_2)
        let endAngle = 0.001 + 1/4 * Double(M_PI) * 70
        let clockwise: Bool = false
        
        // `clockwise` tells the circle whether to animate in a clockwise or anti clockwise direction
        circle.path = UIBezierPath(arcCenter: center, radius: radius, startAngle: CGFloat(startAngle), endAngle: CGFloat(endAngle), clockwise: clockwise).CGPath
        
        let redcolor : UIColor = UIColor(red: (255/255.0), green: (86/255.0), blue: (79/255.0), alpha: 1.0)
        
        circle.strokeColor = redcolor.CGColor
        circle.fillColor = UIColor.clearColor().CGColor
        circle.lineWidth = 8
        
        // When it gets to the end of its animation, leave it at 0% stroke filled
        circle.strokeEnd = 1.0
        circle.strokeStart = 0.0
        
        // Add the circle to the parent layer
        self.layer.addSublayer(circle)
        
        // Configure the animation
        let drawAnimation = CABasicAnimation(keyPath: "strokeStart")
        drawAnimation.repeatCount = 1.0
        
        // Animate from the full stroke being drawn to none of the stroke being drawn
        drawAnimation.fromValue = NSNumber(double: fractionOfCircle)
        drawAnimation.toValue = NSNumber(float: 0.0)
        
        drawAnimation.duration = 1.1
        
        drawAnimation.timingFunction = CAMediaTimingFunction(name: kCAMediaTimingFunctionLinear)
        
        // Add the animation to the circle
        circle.addAnimation(drawAnimation, forKey: "drawCircleAnimation")
    }

}
