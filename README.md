double taxi_fare(int weekday, int start_time, int speed, int distance) {
3
4
    double extra = 0.22;
5
    int run_time = start_time*60;
6
    float org_speed = 50/speed; // meter/sec
7
8
    int dist = 1000;
9
    double fare = 3.4;
10
11
    if(run_time>=360*60 && run_time<540*60){
12
        if(weekday>=1 && weekday<=5){
13
            fare+=fare*0.25;
14
        }
15
    }
16
    else if(run_time>=1080*60 && run_time<1440*60){
17
        fare+=fare*0.25;
18
    }
19
    else if(run_time>=0 && run_time<360*60){
20
        fare+=fare*0.50;
21
    }
22
    else{
23
        fare+=0;
24
    }
25
26
////////////////////////////////////////
27
28
    if(distance>dist){
29
        run_time+= (1000/org_speed);
30
31
        while(dist<distance && dist<10000){
32
            dist+= 400;
33
34
            if(run_time>=360*60 && run_time<540*60){
35
        if(weekday>=1 && weekday<=5){
36
            fare+=(extra + (extra*0.25));
37
        }
38
            }
39
    
40
    else if(run_time>=1080*60 && run_time<1440*60){
41
        fare+=(extra + (extra*0.25));
42
    }
43
    else if(run_time>=0 && run_time<360*60){
44
        fare+=(extra + (extra*0.50));
45
    }
46
    else{
47
        fare+=extra;
48
    }
49
50
    run_time+=(400/org_speed);
51
        }
52
53
 /////////////////////////////////////////     
54
55
        while(dist<distance){
56
            dist+=350;
57
58
            if(run_time>=360*60 && run_time<540*60){
59
        if(weekday>=1 && weekday<=5){
60
            fare+=(extra + (extra*0.25));
61
        }
62
    }
63
    else if(run_time>=1080*60 && run_time<1440*60){
64
        fare+=(extra + (extra*0.25));
65
    }
66
    else if(run_time>=0 && run_time<360*60){
67
        fare+=(extra + (extra*0.50));
68
    }
69
    else{
70
        fare+=extra;
71
    }
72
    run_time+=(350/org_speed);
73
        }
74
    }
75
76
return fare;
77
}
78
