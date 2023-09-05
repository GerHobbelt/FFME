# FFME

Key points detection (OpenCV)

This method is a SIFT-like one, but specifically designed for egomotion computation. The key idea is that it avoids some of the steps SIFT gives, so that it runs faster, at the cost of not being so robust against scaling. The good news is that in egomotion estimation the scaling is not so critical as in registration applications, where SIFT should be selected.


## References

- https://sourceforge.net/projects/ffme/

