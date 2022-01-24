<script>
   import Header from './UI/Header.svelte';
   import MeetupGrid from './Meetups/MeetupGrid.svelte';

   const meetups = [
     {
       id:'m1',
       title:'Coding Bootcamp',
       subtitle:'Learn to code in 2 hours',
       description:'In this meetup, we will have some experts that teach you how to code properly in all ways',
       imageUrl:'https://en.wikipedia.org/wiki/Wikipedia:Meetup#/media/File:WikiConference_USA_2015_Group_Photo_32.JPG',
       address:'27th Nerd Road, 32523 New York',
       contactEmail:'code@test.com'
     },
     {
       id:'m2',
       title:'Coding Bootcamp',
       subtitle:'Learn to code in 2 hours',
       description:'In this meetup, we will have some experts that teach you how to code properly in all ways',
       imageUrl:'https://en.wikipedia.org/wiki/Wikipedia:Meetup#/media/File:WikiConference_USA_2015_Group_Photo_32.JPG',
       address:'27th Nerd Road, 32523 New York',
       contactEmail:'code@test.com'
     },
     {
       id:'m3',
       title:'Coding Bootcamp',
       subtitle:'Learn to code in 2 hours',
       description:'In this meetup, we will have some experts that teach you how to code properly in all ways',
       imageUrl:'https://en.wikipedia.org/wiki/Wikipedia:Meetup#/media/File:WikiConference_USA_2015_Group_Photo_32.JPG',
       address:'27th Nerd Road, 32523 New York',
       contactEmail:'code@test.com'
     },
     {
       id:'m4',
       title:'Coding Bootcamp',
       subtitle:'Learn to code in 2 hours',
       description:'In this meetup, we will have some experts that teach you how to code properly in all ways',
       imageUrl:'https://en.wikipedia.org/wiki/Wikipedia:Meetup#/media/File:WikiConference_USA_2015_Group_Photo_32.JPG',
       address:'27th Nerd Road, 32523 New York',
       contactEmail:'code@test.com'
     }
   ]
</script>

<style>
  main {
    margin-top: 5rem;
  }
</style>

<Header />

<main>
  <MeetupGrid {meetups}/>
</main>



