<script>
   import Header from './UI/Header.svelte';
   import MeetupGrid from './Meetups/MeetupGrid.svelte';
   import TextInput from './UI/TextInput.svelte';
   import Button from './UI/Button.svelte';
   import Modal from './Modal.svelte';

   let title="";
   let subtitle="";
   let address="";
   let email="";
   let description="";
   let imageUrl="";
   let showForm;

   let meetups = [
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

   function addMeetup() {
     const newMeetup = {
       id:Math.random().toString(),
       title:title,
       subtitle:subtitle,
       description:description,
       imageUrl:imageUrl,
       address:address,
       contactEmail:email
     };

     meetups = [...meetups, newMeetup]
   }
</script>

<style>
  main {
    margin-top: 5rem;
  }

  form {
    width: 30rem;
    max-width: 90%;
    margin: auto;
  }
</style>

<Header />

<main>
  <button on:click={() => (showForm = true)}>Add Meetup</button>
  <MeetupGrid {meetups}/>
</main>
{#if showForm}
<Modal on:close="{() => (showForm = false)}">
  <form on:submit|preventDefault="{addMeetup}">
    <TextInput id="title" label="Title" type="text" value={title} on:input="{event => (title = event.target.value)}" />
    <TextInput id="subtitle" label="Subtitle" type="text" value={subtitle} on:input="{event => (subtitle = event.target.value)}" /> 
    <TextInput id="address" label="Address" type="text" value={address} on:input="{event => (address = event.target.value)}" /> 
    <TextInput id="imageUrl" label="Image Url" type="text" value={imageUrl} on:input="{event => (imageUrl = event.target.value)}" /> 
    <TextInput id="email" label="Email" type="email" value={email} on:input="{event => (email = event.target.value)}" />   
    <TextInput id="description" label="Description" controlType="textarea" value={description} on:input="{event => (description = event.target.value)}" />     
    <Button type="submit" caption="Save"/>
  </form>
  <button slot="footer" on:click="{() => (showForm = false)}">Confirm Details</button>
</Modal>
{/if}



