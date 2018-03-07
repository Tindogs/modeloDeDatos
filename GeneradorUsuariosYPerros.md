Para generar los usuarios y perros con https://next.json-generator.com
```
[
  {
    'repeat(5, 10)': {
      _id: '{{objectId()}}',
      first_name: '{{firstName()}}',
      last_name: '{{surname()}}',
      phone: '+34 {{phone()}}',
      mobile_phone: '+34 {{phone()}}',
      email: function (tags) {
        // Email tag is deprecated, because now you can produce an email as simple as this:
        return (this.first_name + '.' + this.last_name + '@' + 'domain' + tags.domainZone()).toLowerCase();
      },
      username: 'User{{index()}}',
      password: 'Pss{{index()}}',
      coordinates: ['{{floating(-90.000001, 90)}}', '{{floating(-180.000001, 180)}}'],
      dogs:[
        {'repeat(0,3)':{
            owner_id: function (tags) {
             return (this._id);
           },
          dog_id:  '{{objectId()}}',
          name:'{{firstName()}}',
          age:  '{{integer(0, 20)}}',
          breed: '{{random("Affenpinscher","Afghan Hound","Afghan Shepherd","Aidi","Airedale Terrier","Akbash","Akita","Alano Español","Alaskan husky","Alaskan Klee Kai","Alaskan Malamute","Alopekis","Alpine Dachsbracke","American Akita","American Bulldog","American Cocker Spaniel","American English Coonhound","American Eskimo Dog","American Foxhound","American Hairless Terrier")}}',
          purebreed: '{{bool()}}',
          color: '{{lorem(1,"sentences")}}',
          query: { 
            age:  '{{integer(0, 20)}}',
            breed: '{{random("Affenpinscher","Afghan Hound","Afghan Shepherd","Aidi","Airedale Terrier","Akbash","Akita","Alano Español","Alaskan husky","Alaskan Klee Kai","Alaskan Malamute","Alopekis","Alpine Dachsbracke","American Akita","American Bulldog","American Cocker Spaniel","American English Coonhound","American Eskimo Dog","American Foxhound","American Hairless Terrier")}}',
            purebreed: '{{bool()}}',
            max_kms: '{{floating(0.5, 5)}}'
          },
          likes_from_others: [
            { 'repeat(0,3)':{
               dog_like_id: '{{objectId()}}',
              owner_id:  '{{objectId()}}'
            }
             
          }],
          description: '{{lorem(3, "sentences")}}',
          photos: []
        }
        }
      ]
    }
  }
]
```