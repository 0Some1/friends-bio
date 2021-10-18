<template>
  <div>
    <b-card-group class="w-75 m-auto" deck>
      <b-card title="Rachel Green" img-height="500px" img-src="../assets/rachel.jpg" img-alt="Image" img-top>
        <b-card-text>
          Rachel Karen Green is a fictional character, one of the six main characters who appeared in the American sitcom Friends. Portrayed by Jennifer Aniston, the character was created by David Crane and Marta Kauffman, and appeared in all of the show's 236 episodes during its decade-long run, from its premiere on September 22, 1994 to its finale on May 6, 2004. Introduced in the show's pilot as a naïve runaway bride who reunites with her childhood best friend Monica Geller and relocates to New York City, Rachel gradually evolves from a spoiled, inexperienced "daddy's girl" into a successful businesswoman. During the show's second season, the character becomes romantically involved with Monica's brother, Ross, with whom she maintains a complicated on-off relationship throughout the series. Together, Ross and Rachel have a daughter, Emma.
        </b-card-text>
        <template #footer>
          <small class="text-muted">Last updated 3 mins ago</small>
        </template>
      </b-card>

      <b-card title="Ross Geller" img-height="500px" img-src="../assets/ross.jpg" img-alt="Image" img-top>
        <b-card-text>
          Ross Geller, Ph.D., portrayed by David Schwimmer, is one of the six main fictional characters of the NBC sitcom Friends. Ross is considered by many to be the most intelligent member of the group and is noted for his goofy but lovable demeanor. His relationship with Rachel Green was included in TV Guide's list of the best TV couples of all time, as well as Entertainment Weekly's "30 Best 'Will They/Won't They?' TV Couples".Kevin Bright who was one of the executive producers of the show, had worked with Schwimmer before, so the writers were already developing Ross's character in Schwimmer's voice. Hence, Schwimmer was the first person to be cast on the show.
        </b-card-text>
        <template #footer>
          <small class="text-muted">Last updated 3 mins ago</small>
        </template>
      </b-card>

      <b-card title="Monica Geller" img-height="500px" img-src="../assets/monica.jpg" img-alt="Image" img-top>
        <b-card-text>
          Monica E. Geller-Bing is a fictional character, one of the six main characters who appears on the American sitcom Friends (1994–2004). Created by David Crane and Marta Kauffman, and portrayed by actress Courteney Cox, Monica appears in all of the show's 236 episodes, from its premiere in 1994, to its finale in 2004. A chef known for her cleanliness, competitiveness and obsessive-compulsive nature, Monica is the younger sister of Ross Geller and best friend of Rachel Green, the latter of whom she invites to live with her after Rachel forsakes her own wedding. The two characters spend several years living together as roommates until Monica begins a romantic relationship with long-time neighbor and friend Chandler Bing, whom she marries. Unable to conceive children on their own, Chandler and Monica eventually adopt twins Erica and Jack and move out of their apartment into a larger house in the suburbs.
        </b-card-text>
        <template #footer>
          <small class="text-muted">Last updated 3 mins ago</small>
        </template>
      </b-card>



    </b-card-group>
    <div class="m-5"></div>


    <b-card-group class="w-75 m-auto" deck>
      <b-card title="Joey Tribbiani" img-height="500px" img-src="../assets/JoeyTribbiani.jpg" img-alt="Image" img-top>
        <b-card-text>
          Joseph Francis Tribbiani Jr. is a fictional character, serving as one of the primary characters of the NBC sitcom Friends and the main protagonist of its spin-off Joey. He is portrayed by Matt LeBlanc in both series.[1]

          He is an Italian-American struggling actor who lives in New York City with his roommate and best friend, Chandler Bing (Matthew Perry), and hangs out in a tight-knit group of his best friends: Chandler, Ross Geller (David Schwimmer), Monica Geller (Courteney Cox), Rachel Green (Jennifer Aniston), and Phoebe Buffay (Lisa Kudrow). He lived with a few other roommates when Chandler moved out to move in with Monica.
        </b-card-text>
        <template #footer>
          <small class="text-muted">Last updated 3 mins ago</small>
        </template>
      </b-card>

      <b-card title="Phoebe Buffay" img-height="500px" img-src="../assets/pheobe.jpg" img-alt="Image" img-top>
        <b-card-text>

          Phoebe Buffay is a character portrayed by Lisa Kudrow, one of the six main characters from the American sitcom Friends, created by David Crane and Marta Kauffman.

          In the series' universe, Phoebe was born on February 16 and is the daughter of Frank and Lily Buffay. Her birth mother's name was Phoebe Abbott, whom she was named after. Phoebe has a twin sister, Ursula, a waitress who is also portrayed by Kudrow. Phoebe can speak several languages, including French and Italian. She appeared in all of the show's 236 episodes. She is a masseuse and musician, notable for her offbeat and extremely ditzy behavior. She was Monica Geller's roommate before Rachel Green, which is how she was introduced to the group.

        </b-card-text>
        <template #footer>
          <small class="text-muted">Last updated 3 mins ago</small>
        </template>
      </b-card>

      <b-card title="Chandler Bing" img-height="500px" img-src="../assets/chandler.jpg" img-alt="Image" img-top>
        <b-card-text>
          Chandler Muriel Bing is a fictional character from the NBC sitcom Friends, portrayed by actor Matthew Perry.[2] Chandler was born to Nora Tyler Bing, an erotic romance novelist, and Charles Bing, a gay female impersonator and star of a Las Vegas drag show called "Viva Las Gay-gas" as Helena Handbasket. Chandler is of Scottish and Swedish descent.[citation needed] He is an only child and is apparently from an affluent family.[citation needed] His parents announced their divorce to him over Thanksgiving dinner when Chandler was nine years old, an event which causes him to refuse to celebrate the holiday in his adulthood and develop his notorious sense of humour as a defense mechanism. It is revealed in season 1 that he went to an all-boys high school.
        </b-card-text>
        <template #footer>
          <small class="text-muted">Last updated 3 mins ago</small>
        </template>
      </b-card>



    </b-card-group>


  </div>
</template>

<script>
export default {
  name: "Cast"
}
</script>

<style scoped>

img{
  object-fit: cover;
}

</style>