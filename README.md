double taxi_fare(int weekday, int start_time, int speed, int distance) {
   double extra = 0.22;
    int run_time = start_time*60;
    float org_speed = 50/speed; // meter/sec
    int dist = 1000;
    double fare = 3.4;
    
    if(run_time>=360*60 && run_time<540*60){
        if(weekday>=1 && weekday<=5){
            fare+=fare*0.25;
        }
    }
    else if(run_time>=1080*60 && run_time<1440*60){
        fare+=fare*0.25;
    }
    else if(run_time>=0 && run_time<360*60){
        fare+=fare*0.50;
    }
    else{
        fare+=0;
    }
    
////////////////////////////////////////

    if(distance>dist){
        run_time+= (1000/org_speed);
        
        while(dist<distance && dist<10000){
            dist+= 400;

            if(run_time>=360*60 && run_time<540*60){
        if(weekday>=1 && weekday<=5){
            fare+=(extra + (extra*0.25));
        }
            }
    
    else if(run_time>=1080*60 && run_time<1440*60){
        fare+=(extra + (extra*0.25));
    }
    else if(run_time>=0 && run_time<360*60){
        fare+=(extra + (extra*0.50));
    }
    else{
        fare+=extra;
    }
    run_time+=(400/org_speed);
        }

 /////////////////////////////////////////     

        while(dist<distance){

            dist+=350;

            if(run_time>=360*60 && run_time<540*60){
        if(weekday>=1 && weekday<=5){
            fare+=(extra + (extra*0.25));
        }
    }
    else if(run_time>=1080*60 && run_time<1440*60){
        fare+=(extra + (extra*0.25));
    }
    else if(run_time>=0 && run_time<360*60){
        fare+=(extra + (extra*0.50));
    }
    else{
        fare+=extra;
    }
    run_time+=(350/org_speed);
        }
    }

return fare;
}
