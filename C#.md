```
Scaleform s = new Scaleform("mp_car_stats_01");
        bool doneScaleformInit = false;
        public BasicResourceClient()
        {
            Tick += OnTick;
        }
        public async Task OnTick()
        {
            if (s.IsLoaded)
            {
                if (doneScaleformInit)
                {
                    s.Render2D();
                }
                else
                {
                    s.CallFunction("SET_VEHICLE_INFOR_AND_STATS", "RE-7B", "Tracked and Insured", "MPCarHUD", "Annis", "Top Speed", "Acceleration", "Braking", "Traction", 68, 60, 40, 70);
                    doneScaleformInit = true;
                }
            }
        }
```
