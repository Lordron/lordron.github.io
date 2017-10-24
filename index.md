## Welcome to my Page

<!DOCTYPE html>
<html>
   <head>
   
      <script type="text/javascript">
         <!--
            function GetChanceAgainst(ownRating, opponentRating)
            {
                return 1.0 / (1 + Math.exp(Math.log(10) * (opponentRating - ownRating) / 650))
            }
            
            function GetRatingMod(ownRating, opponentRating, won)
            {
                var chance = GetChanceAgainst(ownRating, opponentRating)
                var won_mod = won ? 1 : 0
                if (won && ownRating < 1300)
                {
                    if (ownRating < 1000)
                        return Math.ceil(48 * (won_mod - chance))
                    else
                        return Math.ceil((24 + (24 * (1300 - ownRating) / 300)) * (won_mod - chance))
                }
                else
                    return Math.ceil(24 * (won_mod - chance))
            }
            
            function GetMatchmakerRatingMod(ownRating, opponentRating, won)
            {
                var chance = GetChanceAgainst(ownRating, opponentRating)
                var won_mod = won ? 1 : 0
                return Math.ceil(24 * (won_mod - chance))
            }

            function Test()
            {
                
                alert(GetMatchmakerRatingMod(document.getElementById("firstMMR").value, document.getElementById("secondMMR").value, document.getElementById("outcome_won").checked))
            }
         //-->
      </script>
      
   </head>
   <form>
    My Team MMR:<br> <input type="number" name="firstMMR" id="firstMMR" min="1" max="4000" value="1500" size="5"><br><br>
    Opponents Team MMR:<br><input type="number" name="secondMMR" id="secondMMR" min="1" max="4000" value="1500" size="5"><br><br>
    <input type="radio" name="outcome" id="outcome_won" value="hasWon"  checked>Won<br>
    <input type="radio" name="outcome" id="outcome_loose" value="hasLoose">Loose<br><br>
   </form> 
   <body>
      <input type="button" onclick="Test()" value="Calculate" />
   </body>
</html>
