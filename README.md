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
固定矩阵类：
Matx33f f33(1,1,1,2,2,2)表示一个3x3的矩阵；
Vec3f f3(1,2,3)表示一个列为3，行为1的矩阵；

Mat类是一个任意多维数组，它的数据类型为CV_{8U,16S,16U,32S,32F,64F}C{1,2,3}的多种组合；
Mat m,m.create(3,10,CV_32FC3),m.setTo(Scalar(1.0,0.0,1.0));；创建一个3行10列的数据，数据类型为32位的float型，为3通道；
Mat m(3,10,CV_32FC3,Scalar(1.0,0.0,1.0));
构造函数，Mat(int rows,int cols,int type,Scalar()),Mat(Size s,int type,Scalar());Mat(Mat a ,Rect rc);
m1 = m0.clone(),m0.copyTo(m1);


