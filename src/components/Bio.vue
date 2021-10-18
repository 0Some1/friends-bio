<template>
  <b-container class="shadow-sm rounded-lg" fluid >
    <b-row class="align-items-center">
      <b-col class="bg-dark p-0 "  lg="4" md="6" sm="12">
        <img class="w-100 h-100 img rounded-lg" src="../assets/card0.jpg" alt="card">
      </b-col>
      <b-col  class="pre-scrollable text-left m-auto"  lg="8" md="6" sm="12">{{ txt }}</b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Bio",
  data(){
    return{
        txt:`Friends is an American situation comedy about six 20-30s-year old friends living in the New York City borough of Manhattan. It was created by David Crane and Marta Kauffman, which premiered on NBC on September 22, 1994. The series was produced by Bright/Kauffman/Crane Productions, in association with Warner Bros. Television. The original executive producers were Crane, Kauffman and Kevin Bright, with Adam Chase, Michael Curtis, Greg Malins, Scott Silveri, Shana Goldberg-Meehan, Andrew Reich and Ted Cohen being promoted in later seasons.

After originally considering using a well known pop song, REM's Shiny Happy People , the decision was made to compose a theme song for the series. This was I'll Be There For You which was performed by The Rembrandts.
Crane and Kauffman began developing Friends under the title "Insomnia Cafe" in November 1993. They presented the idea to Bright, with whom they had previously worked, and together they pitched a seven-page treatment of the series to NBC. After several script rewrites and changes, the series was finally named "Friends" and premiered on NBC's coveted Thursday 8:30 pm timeslot. Filming for the series took place at Warner Bros. Studios in Burbank, California in front of a live audience. After ten seasons on the network, the series finale was heavily promoted by NBC, and viewing parties were organized around the U.S.. The finale, which was first aired on May 6, 2004, was watched by an average of 52.5 million American viewers, making it the fourth most-watched series finale in television history.`
    }
  }
}
</script>

<style scoped>

.img{
  object-fit: fill;
}
</style>