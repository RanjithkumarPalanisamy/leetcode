
<?php
class College{
    const name="park college";
}
class Course{
    protected static $course=array("1001"=>"BCA","1002"=>"MBA","1003"=>"M.com");
    static function getCourseDetails(){
        var_dump(self::$course);
    }
}
class Campaign extends Course{
    function getCollegeDetails(){
      print College::name;   
      self::getCourseDetails(); 
    }
}

interface Assignment{
    function getAssignment();
}
interface Test{
    function getTestDate();
    function getTestScore();
}
class Student extends Course implements Assignment, Test {
    private static $studId=1000;
    private $studName;
    private $studCourse;
   public function __construct($a,$b,$id){
    // private static $course=array("1001"=>"BCA","1002"=>"MBA","1003"=>"M.com");
    self::$studId=$a;
    $this->studName=$b;
    $this->studCourse=self::$course[$id];

   } 
   public function getStudDetails(){
       print "Name:".$this->studName."\nCourse:".$this->studCourse;
       print "ID:".self::$studId;
   } 
   function getAssignment(){
        print "Php Assignment";
   }
   function getTestDate(){
    print "Php testDate";
   }

   function getTestScore(){
    print "Php Score";
   }
}

$surya=new Student(1000,"surya","1001");
$surya->getStudDetails();
$broucher=new Campaign();
$broucher->getCollegeDetails();
