class Program
    {
        static void Main(string[] args)
        {
            var video = new Video() { Title = "Title" };
            var videoecoder = new VideoEncoder(); //Publisher
            var mailservice = new MailService(); //subscriber
            var messageservice = new MessageService(); //subscriber            
            videoecoder.VideoEncoded += mailservice.OnVideoEncoded;
            videoecoder.VideoEncoded += messageservice.OnVideoEncoded;

            videoecoder.Encode(video); //it we removes it the event & deleget will not work

            Thread.Sleep(3000);
        }

        /*
        public class MailService {
            public void OnVideoEncoded(object source, EventArgs e) { Console.WriteLine("Mail service sending an email.."); }
        }
        
        public class MessageService {
            public void OnVideoEncoded(object source, EventArgs e) { Console.WriteLine("Message service sending a text message.."); }
        }

        public class VideoEncoder
        {
            //1 - Define a delegate
            //2 - define an event based on that delegate
            //3 - Raise the event

            public delegate void VideoEncodedEventHandler(object source, EventArgs args); //1
            public event VideoEncodedEventHandler VideoEncoded; //subscribers //2

            public void Encode(Video video)
            {
                Console.WriteLine("Encoding video..");
                Thread.Sleep(3000);

                OnVideoEncoded(); //this method will notify all subscribers
            }

            protected virtual void OnVideoEncoded() //Evnet publisher method should be protected and vitual, name should start with On
            {
                //this: publisher ie.current class, who is publishing the event
                //EventArgs.Empty : do you want to send any additional data with event, i would say no.
                if (VideoEncoded != null) //if shouldn't be subcriber there then raise event 
                    VideoEncoded(this, EventArgs.Empty);


                //if (VideoEncodedArgs != null)
                //    VideoEncodedArgs(this, new VideoEventArgs() { Video = video }); 

            }
        }
        */

        /*
        //Pass data that event was happened
        public class MailService
        {
            public void OnVideoEncoded(object source, VideoEventArgs e) { Console.WriteLine("Mail service sending an email.." + e.Video.Title); }
        }

        public class MessageService
        {
            public void OnVideoEncoded(object source, VideoEventArgs e) { Console.WriteLine("Message service sending a text message.." + e.Video.Title); }
        }

        public class VideoEncoder
        {
            //1 - Define a delegate
            //2 - define an event based on that delegate
            //3 - Raise the event
            public delegate void VideoEncodedEventHandler(object source, VideoEventArgs args); //1
            public event VideoEncodedEventHandler VideoEncoded; //subscribers //2

            public void Encode(Video video)
            {
                Console.WriteLine("Encoding video..");
                Thread.Sleep(3000);

                OnVideoEncoded(video); //this method will notify all subscribers
            }

            protected virtual void OnVideoEncoded(Video video) //Evnet publisher method should be protected and vitual, name should start with On
            {
                //this: publisher ie.current class, who is publishing the event
                //EventArgs.Empty : do you want to send any additional data with event, i would say no.
                if (VideoEncoded != null)  //if shouldn't be subcriber there then raise event 
                    VideoEncoded(this, new VideoEventArgs() { Video = video }); 
            }
        }

        public class Video {
             public string Title { get; set; }
        }
        
        public class VideoEventArgs : EventArgs
        {
            public Video Video { get; set; }
        }
        */
        //EventHandler
        //EventHandler<TeventArgs>

        //Pass data that event was happened
        public class MailService
        {
            //ctor -- construcotr creatio
            //cw -- console wirtline
            //propfull -- with get and set method
            //equals --
            //try
            //tryf
            //while
            //ctrl K+F
            // ctrl+tab / ctrl+F6 -- change tabs
            // ctrl+shift+tab / ctrl+shift+F6 -- change tabs back
            //ctrl+,
            //ctrl+M+M
            //alt+enter
            
            public void OnVideoEncoded(object source, VideoEventArgs e) { Console.WriteLine("Mail service sending an email.." + e.Video.Title); }
        }

        public class MessageService
        {
            public void OnVideoEncoded(object source, VideoEventArgs e) { Console.WriteLine("Message service sending a text message.." + e.Video.Title); }
        }

        public class VideoEncoder
        {
            public event EventHandler<VideoEventArgs> VideoEncoded; //subscribers //2

            public void Encode(Video video)
            {
                Console.WriteLine("Encoding video..");
                Thread.Sleep(3000);

                OnVideoEncoded(video); //this method will notify all subscribers
            }

            protected virtual void OnVideoEncoded(Video video) //Evnet publisher method should be protected and vitual, name should start with On
            {
                //this: publisher ie.current class, who is publishing the event
                //EventArgs.Empty : do you want to send any additional data with event, i would say no.
                if (VideoEncoded != null)  //if shouldn't be subcriber there then raise event 
                    VideoEncoded(this, new VideoEventArgs() { Video = video });
            }
        }

        public class Video
        {
            public string Title { get; set; }
        }

        public class VideoEventArgs : EventArgs
        {
            public Video Video { get; set; }
        }


    }
