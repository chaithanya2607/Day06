# Day06
# 1] https://github.com/rvsp/typescript-oops/blob/master/Practice/Movie.md.
ANSWER
---
    class Movie {
    constructor(title,studio,rating="PG")
      {
      this.title=title;
      this.studio=studio;
      this.rating=rating;
      }

      static getPg(movie)
       { 
     let moviePg=[]
      movie.forEach(element => {
          if(element.rating =="PG")
          moviePg.push(element)
      });
      return moviePg


      }
    }
     let newMovie1=new Movie("Casino Royale","Eon Productions","PG-13");
     let newMovie2=new Movie("mersal","thenandal","PG");
     let newMovie3=new Movie("beast","sun",);
     let arr=[newMovie1,newMovie2,newMovie3]
     let PGMovies=Movie.getPg(arr)
         console.log(PGMovies);


# 2] https://github.com/rvsp/typescript-oops/blob/master/Practice/class-circle.md.
ANSWER
----


# 3] Write a “person” class to hold all the details.
ANSWER
----
     class Person{
    constructor(name,age,qualification,job,country)
      {
        this.name=name;
        this.age=age;
        this.qualification=qualification;
        this.job=job;
        this.country=country;
        this.fulldetails = function(){
            return [this.name+"  "+this.age+"  "+this.qualification+"  "+this.job+"  "+this.country];
          }
      }
       }
      let person=new Person ( "Manohar","27","Engineering-Graduate","Quality-supervisor","India" )
      console.log(person.fulldetails());

# 4] Write a class to calculate uber price.
ANSWER
----
    var uberClientId = ""
    var uberServerToken = "";
    var userLatitude
    , userLongitude
    , partyLatitude = 19.3256725
    , partyLongitude = -43.1579731;

   navigator.geolocation.watchPosition(function(position) {
    userLatitude = position.coords.latitude;
    userLongitude = position.coords.longitude;
    getEstimatesForUserLocation(userLatitude, userLongitude);
   });
   function getEstimatesForUserLocation(latitude,longitude) {
   $.ajax({
   url: "https://api.uber.com/v1/estimates/price",
   headers: {
       Authorization: "" + uberServerToken
     },
   data: { 
     start_latitude: latitude,
     start_longitude: longitude,
     end_latitude: partyLatitude,
     end_longitude: partyLongitude
      },
   success: function(result) {
     console.log(result);
       }
     });
    }
