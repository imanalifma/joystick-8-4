package org.firstinspires.ftc.teamcode;

import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.eventloop.opmode.LinearOpMode;
import com.qualcomm.robotcore.hardware.DcMotor;
@TeleOp

public class Fatima5 extends LinearOpMode {
  DcMotor backLeft;
  DcMotor backRight;
  DcMotor frontLeft;
  DcMotor frontRight;
  @Override
  public void runOpMode(){
    
    backLeft = hardwareMap.get(DcMotor.class, "bl");
    backRight = hardwareMap.get(DcMotor.class, "br");
    frontLeft = hardwareMap.get(DcMotor.class, "fl");
    frontRight = hardwareMap.get(DcMotor.class, "fr");
waitForStart();
while(opModeIsActive()){
  float x = this.gamepad1.left_stick_x;
  float y = this.gamepad1.left_stick_y * -1;
  telemetry.addData("Status", "x:" + x+ "y:" + y);
  telemetry.update();
 
  frontLeft.setPower(x-y);
  frontRight.setPower(x+y);
  backLeft.setPower(-x-y);
  backRight.setPower(-x+y);
}
    // todo: write your code here
} 
