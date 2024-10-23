# MasterProject_FSE100




while 1
    pause(0.1);
               
brick.SetColorMode(3, 2);
 touch = brick.TouchPressed(1);
 color = brick.ColorCode(3);
 distance = brick.UltrasonicDist(2);

        if distance <= 40
               display(distance);
                brick.MoveMotor('AB', 50);

        else if touch
                brick.beep();
                display(distance);
                if distance > 40
                brick.StopMotor('AB', 'Coast');
                brick.MoveMotor('AB', -50);
                pause(0.5);
                brick.StopMotor('AB', 'Coast');
                
                if distance > 40
                    brick.MoveMotorAngleRel('B', 100, -660, 'Coast');
                end
        end
        end
        end
end
      
