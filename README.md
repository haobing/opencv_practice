# opencv_practice
1、数据类型缩写：
b = unsigned char;
w  = unsigned short;
s = short;
i = int;
f = float;
d = double;

2、常用类型：
Point Point2f,Point3i,访问元素：x,y;
Scalar 它是一个四维点类；
Size Size2f Size2i ,访问元素：width,height;
Rect 矩形类，访问元素，x,y,width,height;
RotatedRect 矩形类，访问元素，center(中心点）,size（大小）,angle（角度）；

3、固定矩阵类：
Matx33f f33(1,1,1,2,2,2)表示一个3x3的矩阵；
Vec3f f3(1,2,3)表示一个列为3，行为1的矩阵；

Mat类是一个任意多维数组，它的数据类型为CV_{8U,16S,16U,32S,32F,64F}C{1,2,3}的多种组合；
Mat m,m.create(3,10,CV_32FC3),m.setTo(Scalar(1.0,0.0,1.0));；创建一个3行10列的数据，数据类型为32位的float型，为3通道；
Mat m(3,10,CV_32FC3,Scalar(1.0,0.0,1.0));
构造函数，Mat(int rows,int cols,int type,Scalar()),Mat(Size s,int type,Scalar());Mat(Mat a ,Rect rc);
m1 = m0.clone(),m0.copyTo(m1);

4、绘图：
cv::circle(Mat &img,Point center,int radius,Scalar color,int thickness = 1,int lineType = 8,int shift = 0);画一个 圆
cv::clipLine(Rect imgRect,Point pt1,Point pt2);判断一条直线是否在给定的圆内；
cv::ellipse(Mat img,Point center,Size axes,double angle,double startAngle,double endAngle,Scalar color,int thickness = 1,int lineType=8,int shift =0); 画一个椭圆；
cv::ellipse2Poly(Point center,Size axes,double angle,double startAngle,double endAngle,int delta,vector<Point> pts);画一个近似椭圆的多边形；
  cv::fillConvexPoly(Mat img,Point,pts,int npts,Scalar color,int lineType = 8, int shift = 0);画一个填充的简单多边形；
  cv::fillPoly(Mat img,Point pts,int npts,int ncontours,Scalar color,int lineType=8,int shift=0,Point offset = Point());画一个填充的任意多边形；
  cv::line(Mat img,Point pt1,Point pt2,Scalar color,int lineType=8,int shift = 0);画一条直线；
  cv::rectangle(Mat img,Rect r,Scalar color,int lineType=8,int shift=0);画一个矩形；
  cv::polyLines(Mat img,Point *pts,int npts,int ncontours,bool isClosed,Scalar color,int lineType=8,int shift=0);画多重折线；

感兴趣区域提取
方法1：
Mat img = imread("1.jpg");
Mat roi = img(Rect(500, 200, 100, 300));//Rect四个形参分别是：x坐标，y坐标，长，高；注意(x,y)指的是矩形的左上角点
方法2：
Mat img = imread("1.jpg");
Mat roi = img(Range(250, 250 + 100), Range(200, 200 + 100));//Range两个形参分别是：起始行或列，起始行或列+偏移量

