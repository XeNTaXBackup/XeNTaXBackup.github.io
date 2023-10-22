## Post #1
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-06-15T17:13:59+00:00
- Post Title: Problem with hex codes...

if(hex == '0') le = "00003B00";
else if(hex == '1') le = "02003B00";
else if(hex == '2') le = "04003B00";
else if(hex == '3') le = "06003B00";
else if(hex == '4') le = "08003B00";
else if(hex == '5') le = "0A003B00";
else if(hex == '6') le = "0C003B00";
else if(hex == '7') le = "0E003B00";
else if(hex == '8') le = "10003B00";
else if(hex == '9') le = "12003B00";
else if(hex == '!') le = "14003B00";
else if(hex == '?') le = "16003B00";
else if(hex == '(') le = "18003B00";
else if(hex == ')') le = "1A003B00";
else if(hex == ' ') le = "1C003B00";
else if(hex == '&') le = "1E003B00";
else if(hex == ':') le = "20003B00";
else if(hex == ';') le = "22003B00";
else if(hex == ',') le = "24003B00";
else if(hex == '.') le = "26003B00";
else if(hex == '|') le = "28003B00";
else if(hex == '^') le = "2A003B00";
else if(hex == '~') le = "2C003B00";
else if(hex == '-') le = "2E003B00";
else if(hex == '+') le = "30003B00";
else if(hex == '/') le = "32003B00";
else if(hex == '@') le = "34003B00";
else if(hex == '$') le = "36003B00";
else if(hex == 'A') le = "38003B00";
else if(hex == 'B') le = "3A003B00";
else if(hex == 'C') le = "3C003B00";
else if(hex == 'D') le = "3E003B00";
else if(hex == 'E') le = "40003B00";
else if(hex == 'F') le = "42003B00";
else if(hex == 'G') le = "44003B00";
else if(hex == 'H') le = "46003B00";
else if(hex == 'I') le = "48003100";
else if(hex == 'J') le = "4A003A00";
else if(hex == 'K') le = "4C003B00";
else if(hex == 'L') le = "4E003B00";
else if(hex == 'M') le = "50003B00";
else if(hex == 'N') le = "52003B00";
else if(hex == 'O') le = "54003B00";
else if(hex == 'P') le = "56003B00";
else if(hex == 'Q') le = "58003B00";
else if(hex == 'R') le = "5A003B00";
else if(hex == 'S') le = "5C003B00";
else if(hex == 'T') le = "5E003B00";
else if(hex == 'U') le = "60003B00";
else if(hex == 'V') le = "62003B00";
else if(hex == 'W') le = "64003B00";
else if(hex == 'X') le = "66003B00";
else if(hex == 'Y') le = "68003B00";
else if(hex == 'Z') le = "6A003B00";
else if(hex == 'a') le = "6C003B00";
else if(hex == 'b') le = "6E003B00";
else if(hex == 'c') le = "70003B00";
else if(hex == 'd') le = "72003B00";
else if(hex == 'e') le = "74003B00";
else if(hex == 'f') le = "76003B00";
else if(hex == 'g') le = "78003B00";
else if(hex == 'h') le = "7A003B00";
else if(hex == 'i') le = "7C003500";
else if(hex == 'j') le = "7E002F00";
else if(hex == 'k') le = "80003B00";
else if(hex == 'l') le = "82003B00";
else if(hex == 'm') le = "84003B00";
else if(hex == 'n') le = "86003B00";
else if(hex == 'o') le = "88003B00";
else if(hex == 'p') le = "8A003B00";
else if(hex == 'q') le = "8C003B00";
else if(hex == 'r') le = "8E003B00";
else if(hex == 's') le = "90003B00";
else if(hex == 't') le = "92003B00";
else if(hex == 'u') le = "94003B00";
else if(hex == 'v') le = "96003B00";
else if(hex == 'w') le = "98003B00";
else if(hex == 'x') le = "9A003B00";
else if(hex == 'y') le = "9C003B00";
else if(hex == 'z') le = "9E003B00";
else if(hex == '_') le = "1A013B00";
else if(hex == '%') le = "00000304";


Hex equivalents of the characters are above. I want to add an extra character but I could not find the hex equivalents.
Example: ö,Ö,ç,Ç,ü,Ü,ş,Ş,ı,İ

Could you help me with this? Thanks...
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2010-06-16T13:04:17+00:00
- Post Title: Problem with hex codes...

Can you explain more that you're trying to do? Where did you get those hex. codes from?

If you're trying to make some text editor or something similar for a game, then you might want to check the original game texts if the game uses those characters, OR just try to guess the character code (you can see the pattern for the hex. codes is pretty simple).
If those characters aren't used by the game, then maybe they aren't in the game font, so you might need to add them.

By the way, this long list of "else ifs" can be replaced by an array (C), std::map (C++) or Dictionary (.NET). Also, are you sure that you want the hex. code in an string instead of in a 32-bit integer?
## Post #3
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-06-16T13:52:56+00:00
- Post Title: Problem with hex codes...

```
import java.io.*;


public class Re5MsgEditor {

public static void main(String[] args)
{


// decoding("mes_event_e");
// decoding("mes_item_e");
// decoding("mes_stage1_e");
// decoding("mes_stage2_e");
// decoding("mes_stage3_e");
// decoding("mes_stage5_e");
// decoding("mes_system_e");
// decoding("mes_file_e");

// encoding("mes_event_e");
// encoding("mes_item_e");
// encoding("mes_stage1_e");
// encoding("mes_stage2_e");
// encoding("mes_stage3_e");
// encoding("mes_stage5_e");
// encoding("mes_system_e");
encoding("mes_file_e");

}

public static void decoding(String fileName)
{

File file = new File("Original\\"+fileName+".txt");
File de_file = new File("Decoded\\"+fileName+"_decoded.txt");

try
{
FileReader fr = new FileReader(file);
BufferedReader br = new BufferedReader(fr);
FileWriter fw = new FileWriter(de_file);
BufferedWriter bw = new BufferedWriter(fw);

for(int j = 0 ; j < 128 ; j++) br.read();

String readString = br.readLine();
String Hex ="";

int count = 0;


for(int i = 0 ; i < readString.length() ; i++)
{
count++;

Hex = Hex + readString.charAt(i);
if(count == 8)
{
if(!Hex.equalsIgnoreCase("00000104"))
{
if(fileName.equalsIgnoreCase("mes_item_e")) bw.write(find_mes_item_e_Alpa(Hex));
else bw.write(findAlpa(Hex));

}else
{
bw.write("#");
bw.newLine();
}

Hex = "";
count = 0;
}

}
br.close();
fr.close();
bw.close();
fw.close();


}catch(Exception e){}
}

public static void encoding(String fileName)
{

File o_file = new File("Original\\"+fileName+".txt");
File file = new File("Decoded\\"+fileName+"_decoded.txt");
File en_file = new File(fileName+"_encoded.txt");
try
{
FileReader o_fr = new FileReader(o_file);
BufferedReader o_br = new BufferedReader(o_fr);
FileReader fr = new FileReader(file);
BufferedReader br = new BufferedReader(fr);
FileWriter fw = new FileWriter(en_file);
BufferedWriter bw = new BufferedWriter(fw);

String Ori_Data = o_br.readLine();
String Header = "";
String Code = "";

for(int h = 0 ; h < 128 ; h++ ) Header = Header + Ori_Data.charAt(h);
bw.write(Header);

while(true)
{
Code = br.readLine();

if(Code == null) break;
for(int i = 0 ; i < Code.length() ; i++)
{
char ch = Code.charAt(i);
if(ch == '[')
{
for(int j = 0 ; j < 8 ; j++)
{
i = i + 1;
bw.write(Code.charAt(i));
}
}else if(ch == ']') bw.write("");
else if(ch == '#') bw.write("00000104");

else
{
if(fileName.equalsIgnoreCase("mes_item_e")) bw.write(find_mes_item_e_Hex(ch));
else bw.write(findHex(ch));
}

}
}

o_br.close();
o_fr.close();
br.close();
fr.close();
bw.close();
fw.close();


}catch(Exception e){}
}

public static String findAlpa(String ch)
{

String Alpa = ch;

if(Alpa.equalsIgnoreCase("00003B00")) Alpa ="0";
else if(Alpa.equalsIgnoreCase("02003B00")) Alpa ="1";
else if(Alpa.equalsIgnoreCase("04003B00")) Alpa ="2";
else if(Alpa.equalsIgnoreCase("06003B00")) Alpa ="3";
else if(Alpa.equalsIgnoreCase("08003B00")) Alpa ="4";
else if(Alpa.equalsIgnoreCase("0A003B00")) Alpa ="5";
else if(Alpa.equalsIgnoreCase("0C003B00")) Alpa ="6";
else if(Alpa.equalsIgnoreCase("0E003B00")) Alpa ="7";
else if(Alpa.equalsIgnoreCase("10003B00")) Alpa ="8";
else if(Alpa.equalsIgnoreCase("12003B00")) Alpa ="9";
else if(Alpa.equalsIgnoreCase("14003B00")) Alpa ="!";
else if(Alpa.equalsIgnoreCase("16003B00")) Alpa ="?";
else if(Alpa.equalsIgnoreCase("18003B00")) Alpa ="(";
else if(Alpa.equalsIgnoreCase("1A003B00")) Alpa =")";
else if(Alpa.equalsIgnoreCase("1C003B00")) Alpa =" ";
else if(Alpa.equalsIgnoreCase("1E003B00")) Alpa ="&";
else if(Alpa.equalsIgnoreCase("20003B00")) Alpa =":";
else if(Alpa.equalsIgnoreCase("22003B00")) Alpa =";";
else if(Alpa.equalsIgnoreCase("24003B00")) Alpa =",";
else if(Alpa.equalsIgnoreCase("26003B00")) Alpa =".";
else if(Alpa.equalsIgnoreCase("28003B00")) Alpa ="|";
else if(Alpa.equalsIgnoreCase("2A003B00")) Alpa ="^";
else if(Alpa.equalsIgnoreCase("2C003B00")) Alpa ="~";
else if(Alpa.equalsIgnoreCase("2E003B00")) Alpa ="-";
else if(Alpa.equalsIgnoreCase("30003B00")) Alpa ="+";
else if(Alpa.equalsIgnoreCase("32003B00")) Alpa ="/";
else if(Alpa.equalsIgnoreCase("34003B00")) Alpa ="@";
else if(Alpa.equalsIgnoreCase("36003B00")) Alpa ="$";
else if(Alpa.equalsIgnoreCase("38003B00")) Alpa ="A";
else if(Alpa.equalsIgnoreCase("3A003B00")) Alpa ="B";
else if(Alpa.equalsIgnoreCase("3C003B00")) Alpa ="C";
else if(Alpa.equalsIgnoreCase("3E003B00")) Alpa ="D";
else if(Alpa.equalsIgnoreCase("40003B00")) Alpa ="E";
else if(Alpa.equalsIgnoreCase("42003B00")) Alpa ="F";
else if(Alpa.equalsIgnoreCase("44003B00")) Alpa ="G";
else if(Alpa.equalsIgnoreCase("46003B00")) Alpa ="H";
else if(Alpa.equalsIgnoreCase("48003100")) Alpa ="I";
else if(Alpa.equalsIgnoreCase("4A003A00")) Alpa ="J";
else if(Alpa.equalsIgnoreCase("4C003B00")) Alpa ="K";
else if(Alpa.equalsIgnoreCase("4E003B00")) Alpa ="L";
else if(Alpa.equalsIgnoreCase("50003B00")) Alpa ="M";
else if(Alpa.equalsIgnoreCase("52003B00")) Alpa ="N";
else if(Alpa.equalsIgnoreCase("54003B00")) Alpa ="O";
else if(Alpa.equalsIgnoreCase("56003B00")) Alpa ="P";
else if(Alpa.equalsIgnoreCase("58003B00")) Alpa ="Q";
else if(Alpa.equalsIgnoreCase("5A003B00")) Alpa ="R";
else if(Alpa.equalsIgnoreCase("5C003B00")) Alpa ="S";
else if(Alpa.equalsIgnoreCase("5E003B00")) Alpa ="T";
else if(Alpa.equalsIgnoreCase("60003B00")) Alpa ="U";
else if(Alpa.equalsIgnoreCase("62003B00")) Alpa ="V";
else if(Alpa.equalsIgnoreCase("64003B00")) Alpa ="W";
else if(Alpa.equalsIgnoreCase("66003B00")) Alpa ="X";
else if(Alpa.equalsIgnoreCase("68003B00")) Alpa ="Y";
else if(Alpa.equalsIgnoreCase("6A003B00")) Alpa ="Z";
else if(Alpa.equalsIgnoreCase("6C003B00")) Alpa ="a";
else if(Alpa.equalsIgnoreCase("6E003B00")) Alpa ="b";
else if(Alpa.equalsIgnoreCase("70003B00")) Alpa ="c";
else if(Alpa.equalsIgnoreCase("72003B00")) Alpa ="d";
else if(Alpa.equalsIgnoreCase("74003B00")) Alpa ="e";
else if(Alpa.equalsIgnoreCase("76003B00")) Alpa ="f";
else if(Alpa.equalsIgnoreCase("78003B00")) Alpa ="g";
else if(Alpa.equalsIgnoreCase("7A003B00")) Alpa ="h";
else if(Alpa.equalsIgnoreCase("7C003500")) Alpa ="i";
else if(Alpa.equalsIgnoreCase("7E002F00")) Alpa ="j";
else if(Alpa.equalsIgnoreCase("80003B00")) Alpa ="k";
else if(Alpa.equalsIgnoreCase("82003B00")) Alpa ="l";
else if(Alpa.equalsIgnoreCase("84003B00")) Alpa ="m";
else if(Alpa.equalsIgnoreCase("86003B00")) Alpa ="n";
else if(Alpa.equalsIgnoreCase("88003B00")) Alpa ="o";
else if(Alpa.equalsIgnoreCase("8A003B00")) Alpa ="p";
else if(Alpa.equalsIgnoreCase("8C003B00")) Alpa ="q";
else if(Alpa.equalsIgnoreCase("8E003B00")) Alpa ="r";
else if(Alpa.equalsIgnoreCase("90003B00")) Alpa ="s";
else if(Alpa.equalsIgnoreCase("92003B00")) Alpa ="t";
else if(Alpa.equalsIgnoreCase("94003B00")) Alpa ="u";
else if(Alpa.equalsIgnoreCase("96003B00")) Alpa ="v";
else if(Alpa.equalsIgnoreCase("98003B00")) Alpa ="w";
else if(Alpa.equalsIgnoreCase("9A003B00")) Alpa ="x";
else if(Alpa.equalsIgnoreCase("9C003B00")) Alpa ="y";
else if(Alpa.equalsIgnoreCase("9E003B00")) Alpa ="z";
else if(Alpa.equalsIgnoreCase("1A013B00")) Alpa ="_";
else if(Alpa.equalsIgnoreCase("00000304")) Alpa ="%";

else
{

Alpa = "["+ch+"]";
//System.out.println(Alpa);
}

return Alpa;
}

public static String findHex(char ch)
{
String le = "";
char hex = ch;


if(hex == '0') le = "00003B00";
else if(hex == '1') le = "02003B00";
else if(hex == '2') le = "04003B00";
else if(hex == '3') le = "06003B00";
else if(hex == '4') le = "08003B00";
else if(hex == '5') le = "0A003B00";
else if(hex == '6') le = "0C003B00";
else if(hex == '7') le = "0E003B00";
else if(hex == '8') le = "10003B00";
else if(hex == '9') le = "12003B00";
else if(hex == '!') le = "14003B00";
else if(hex == '?') le = "16003B00";
else if(hex == '(') le = "18003B00";
else if(hex == ')') le = "1A003B00";
else if(hex == ' ') le = "1C003B00";
else if(hex == '&') le = "1E003B00";
else if(hex == ':') le = "20003B00";
else if(hex == ';') le = "22003B00";
else if(hex == ',') le = "24003B00";
else if(hex == '.') le = "26003B00";
else if(hex == '|') le = "28003B00";
else if(hex == '^') le = "2A003B00";
else if(hex == '~') le = "2C003B00";
else if(hex == '-') le = "2E003B00";
else if(hex == '+') le = "30003B00";
else if(hex == '/') le = "32003B00";
else if(hex == '@') le = "34003B00";
else if(hex == '$') le = "36003B00";
else if(hex == 'A') le = "38003B00";
else if(hex == 'B') le = "3A003B00";
else if(hex == 'C') le = "3C003B00";
else if(hex == 'D') le = "3E003B00";
else if(hex == 'E') le = "40003B00";
else if(hex == 'F') le = "42003B00";
else if(hex == 'G') le = "44003B00";
else if(hex == 'H') le = "46003B00";
else if(hex == 'I') le = "48003100";
else if(hex == 'J') le = "4A003A00";
else if(hex == 'K') le = "4C003B00";
else if(hex == 'L') le = "4E003B00";
else if(hex == 'M') le = "50003B00";
else if(hex == 'N') le = "52003B00";
else if(hex == 'O') le = "54003B00";
else if(hex == 'P') le = "56003B00";
else if(hex == 'Q') le = "58003B00";
else if(hex == 'R') le = "5A003B00";
else if(hex == 'S') le = "5C003B00";
else if(hex == 'T') le = "5E003B00";
else if(hex == 'U') le = "60003B00";
else if(hex == 'V') le = "62003B00";
else if(hex == 'W') le = "64003B00";
else if(hex == 'X') le = "66003B00";
else if(hex == 'Y') le = "68003B00";
else if(hex == 'Z') le = "6A003B00";
else if(hex == 'a') le = "6C003B00";
else if(hex == 'b') le = "6E003B00";
else if(hex == 'c') le = "70003B00";
else if(hex == 'd') le = "72003B00";
else if(hex == 'e') le = "74003B00";
else if(hex == 'f') le = "76003B00";
else if(hex == 'g') le = "78003B00";
else if(hex == 'h') le = "7A003B00";
else if(hex == 'i') le = "7C003500";
else if(hex == 'j') le = "7E002F00";
else if(hex == 'k') le = "80003B00";
else if(hex == 'l') le = "82003B00";
else if(hex == 'm') le = "84003B00";
else if(hex == 'n') le = "86003B00";
else if(hex == 'o') le = "88003B00";
else if(hex == 'p') le = "8A003B00";
else if(hex == 'q') le = "8C003B00";
else if(hex == 'r') le = "8E003B00";
else if(hex == 's') le = "90003B00";
else if(hex == 't') le = "92003B00";
else if(hex == 'u') le = "94003B00";
else if(hex == 'v') le = "96003B00";
else if(hex == 'w') le = "98003B00";
else if(hex == 'x') le = "9A003B00";
else if(hex == 'y') le = "9C003B00";
else if(hex == 'z') le = "9E003B00";
else if(hex == '_') le = "1A013B00";
else if(hex == '%') le = "00000304";

else System.out.print(hex);
return le;
}

public static String find_mes_item_e_Alpa(String ch)
{

String Alpa = ch;

if(Alpa.equalsIgnoreCase("00003C00")) Alpa ="0";
else if(Alpa.equalsIgnoreCase("02003C00")) Alpa ="1";
else if(Alpa.equalsIgnoreCase("04003C00")) Alpa ="2";
else if(Alpa.equalsIgnoreCase("06003C00")) Alpa ="3";
else if(Alpa.equalsIgnoreCase("08003C00")) Alpa ="4";
else if(Alpa.equalsIgnoreCase("0A003C00")) Alpa ="5";
else if(Alpa.equalsIgnoreCase("0C003C00")) Alpa ="6";
else if(Alpa.equalsIgnoreCase("0E003C00")) Alpa ="7";
else if(Alpa.equalsIgnoreCase("10003C00")) Alpa ="8";
else if(Alpa.equalsIgnoreCase("12003C00")) Alpa ="9";
else if(Alpa.equalsIgnoreCase("14003C00")) Alpa ="!";
else if(Alpa.equalsIgnoreCase("16003C00")) Alpa ="?";
else if(Alpa.equalsIgnoreCase("18003C00")) Alpa ="(";
else if(Alpa.equalsIgnoreCase("1A003C00")) Alpa =")";
else if(Alpa.equalsIgnoreCase("1C003C00")) Alpa =" ";
else if(Alpa.equalsIgnoreCase("1E003C00")) Alpa ="&";
else if(Alpa.equalsIgnoreCase("20003C00")) Alpa =":";
else if(Alpa.equalsIgnoreCase("22003C00")) Alpa =";";
else if(Alpa.equalsIgnoreCase("24003C00")) Alpa =",";
else if(Alpa.equalsIgnoreCase("26003C00")) Alpa =".";
else if(Alpa.equalsIgnoreCase("28003C00")) Alpa ="|";
else if(Alpa.equalsIgnoreCase("2A003C00")) Alpa ="^";
else if(Alpa.equalsIgnoreCase("2C003C00")) Alpa ="~";
else if(Alpa.equalsIgnoreCase("2E003C00")) Alpa ="-";
else if(Alpa.equalsIgnoreCase("30003C00")) Alpa ="+";
else if(Alpa.equalsIgnoreCase("32003C00")) Alpa ="/";
else if(Alpa.equalsIgnoreCase("34003C00")) Alpa ="@";
else if(Alpa.equalsIgnoreCase("36003C00")) Alpa ="$";
else if(Alpa.equalsIgnoreCase("38003C00")) Alpa ="A";
else if(Alpa.equalsIgnoreCase("3A003C00")) Alpa ="B";
else if(Alpa.equalsIgnoreCase("3C003C00")) Alpa ="C";
else if(Alpa.equalsIgnoreCase("3E003C00")) Alpa ="D";
else if(Alpa.equalsIgnoreCase("40003C00")) Alpa ="E";
else if(Alpa.equalsIgnoreCase("42003C00")) Alpa ="F";
else if(Alpa.equalsIgnoreCase("44003C00")) Alpa ="G";
else if(Alpa.equalsIgnoreCase("46003C00")) Alpa ="H";
else if(Alpa.equalsIgnoreCase("48003C00")) Alpa ="I";
else if(Alpa.equalsIgnoreCase("4A003C00")) Alpa ="J";
else if(Alpa.equalsIgnoreCase("4C003C00")) Alpa ="K";
else if(Alpa.equalsIgnoreCase("4E003C00")) Alpa ="L";
else if(Alpa.equalsIgnoreCase("50003C00")) Alpa ="M";
else if(Alpa.equalsIgnoreCase("52003C00")) Alpa ="N";
else if(Alpa.equalsIgnoreCase("54003C00")) Alpa ="O";
else if(Alpa.equalsIgnoreCase("56003C00")) Alpa ="P";
else if(Alpa.equalsIgnoreCase("58003C00")) Alpa ="Q";
else if(Alpa.equalsIgnoreCase("5A003C00")) Alpa ="R";
else if(Alpa.equalsIgnoreCase("5C003C00")) Alpa ="S";
else if(Alpa.equalsIgnoreCase("5E003C00")) Alpa ="T";
else if(Alpa.equalsIgnoreCase("60003C00")) Alpa ="U";
else if(Alpa.equalsIgnoreCase("62003C00")) Alpa ="V";
else if(Alpa.equalsIgnoreCase("64003C00")) Alpa ="W";
else if(Alpa.equalsIgnoreCase("66003C00")) Alpa ="X";
else if(Alpa.equalsIgnoreCase("68003C00")) Alpa ="Y";
else if(Alpa.equalsIgnoreCase("6A003C00")) Alpa ="Z";
else if(Alpa.equalsIgnoreCase("6C003C00")) Alpa ="a";
else if(Alpa.equalsIgnoreCase("6E003C00")) Alpa ="b";
else if(Alpa.equalsIgnoreCase("70003C00")) Alpa ="c";
else if(Alpa.equalsIgnoreCase("72003C00")) Alpa ="d";
else if(Alpa.equalsIgnoreCase("74003C00")) Alpa ="e";
else if(Alpa.equalsIgnoreCase("76003C00")) Alpa ="f";
else if(Alpa.equalsIgnoreCase("78003C00")) Alpa ="g";
else if(Alpa.equalsIgnoreCase("7A003C00")) Alpa ="h";
else if(Alpa.equalsIgnoreCase("7C003C00")) Alpa ="i";
else if(Alpa.equalsIgnoreCase("7E003C00")) Alpa ="j";
else if(Alpa.equalsIgnoreCase("80003C00")) Alpa ="k";
else if(Alpa.equalsIgnoreCase("82003C00")) Alpa ="l";
else if(Alpa.equalsIgnoreCase("84003C00")) Alpa ="m";
else if(Alpa.equalsIgnoreCase("86003C00")) Alpa ="n";
else if(Alpa.equalsIgnoreCase("88003C00")) Alpa ="o";
else if(Alpa.equalsIgnoreCase("8A003C00")) Alpa ="p";
else if(Alpa.equalsIgnoreCase("8C003C00")) Alpa ="q";
else if(Alpa.equalsIgnoreCase("8E003C00")) Alpa ="r";
else if(Alpa.equalsIgnoreCase("90003C00")) Alpa ="s";
else if(Alpa.equalsIgnoreCase("92003C00")) Alpa ="t";
else if(Alpa.equalsIgnoreCase("94003C00")) Alpa ="u";
else if(Alpa.equalsIgnoreCase("96003C00")) Alpa ="v";
else if(Alpa.equalsIgnoreCase("98003C00")) Alpa ="w";
else if(Alpa.equalsIgnoreCase("9A003C00")) Alpa ="x";
else if(Alpa.equalsIgnoreCase("9C003C00")) Alpa ="y";
else if(Alpa.equalsIgnoreCase("9E003C00")) Alpa ="z";
else if(Alpa.equalsIgnoreCase("1A013C00")) Alpa ="_";
else if(Alpa.equalsIgnoreCase("00000304")) Alpa ="%";

else
{

Alpa = "["+ch+"]";
System.out.println(Alpa);
}

return Alpa;
}

public static String find_mes_item_e_Hex(char ch)
{
String le = "";
char hex = ch;


if(hex == '0') le = "00003C00";
else if(hex == '1') le = "02003C00";
else if(hex == '2') le = "04003C00";
else if(hex == '3') le = "06003C00";
else if(hex == '4') le = "08003C00";
else if(hex == '5') le = "0A003C00";
else if(hex == '6') le = "0C003C00";
else if(hex == '7') le = "0E003C00";
else if(hex == '8') le = "10003C00";
else if(hex == '9') le = "12003C00";
else if(hex == '!') le = "14003C00";
else if(hex == '?') le = "16003C00";
else if(hex == '(') le = "18003C00";
else if(hex == ')') le = "1A003C00";
else if(hex == ' ') le = "1C003C00";
else if(hex == '&') le = "1E003C00";
else if(hex == ':') le = "20003C00";
else if(hex == ';') le = "22003C00";
else if(hex == ',') le = "24003C00";
else if(hex == '.') le = "26003C00";
else if(hex == '|') le = "28003C00";
else if(hex == '^') le = "2A003C00";
else if(hex == '~') le = "2C003C00";
else if(hex == '-') le = "2E003C00";
else if(hex == '+') le = "30003C00";
else if(hex == '/') le = "32003C00";
else if(hex == '@') le = "34003C00";
else if(hex == '$') le = "36003C00";
else if(hex == 'A') le = "38003C00";
else if(hex == 'B') le = "3A003C00";
else if(hex == 'C') le = "3C003C00";
else if(hex == 'D') le = "3E003C00";
else if(hex == 'E') le = "40003C00";
else if(hex == 'F') le = "42003C00";
else if(hex == 'G') le = "44003C00";
else if(hex == 'H') le = "46003C00";
else if(hex == 'I') le = "48003C00";
else if(hex == 'J') le = "4A003C00";
else if(hex == 'K') le = "4C003C00";
else if(hex == 'L') le = "4E003C00";
else if(hex == 'M') le = "50003C00";
else if(hex == 'N') le = "52003C00";
else if(hex == 'O') le = "54003C00";
else if(hex == 'P') le = "56003C00";
else if(hex == 'Q') le = "58003C00";
else if(hex == 'R') le = "5A003C00";
else if(hex == 'S') le = "5C003C00";
else if(hex == 'T') le = "5E003C00";
else if(hex == 'U') le = "60003C00";
else if(hex == 'V') le = "62003C00";
else if(hex == 'W') le = "64003C00";
else if(hex == 'X') le = "66003C00";
else if(hex == 'Y') le = "68003C00";
else if(hex == 'Z') le = "6A003C00";
else if(hex == 'a') le = "6C003C00";
else if(hex == 'b') le = "6E003C00";
else if(hex == 'c') le = "70003C00";
else if(hex == 'd') le = "72003C00";
else if(hex == 'e') le = "74003C00";
else if(hex == 'f') le = "76003C00";
else if(hex == 'g') le = "78003C00";
else if(hex == 'h') le = "7A003C00";
else if(hex == 'i') le = "7C003C00";
else if(hex == 'j') le = "7E003C00";
else if(hex == 'k') le = "80003C00";
else if(hex == 'l') le = "82003C00";
else if(hex == 'm') le = "84003C00";
else if(hex == 'n') le = "86003C00";
else if(hex == 'o') le = "88003C00";
else if(hex == 'p') le = "8A003C00";
else if(hex == 'q') le = "8C003C00";
else if(hex == 'r') le = "8E003C00";
else if(hex == 's') le = "90003C00";
else if(hex == 't') le = "92003C00";
else if(hex == 'u') le = "94003C00";
else if(hex == 'v') le = "96003C00";
else if(hex == 'w') le = "98003C00";
else if(hex == 'x') le = "9A003C00";
else if(hex == 'y') le = "9C003C00";
else if(hex == 'z') le = "9E003C00";

else if(hex == '_') le = "1A013C00";
else if(hex == '%') le = "00000304";

else System.out.print(hex);
return le;
}



}

--------source end----------- 
```
## Post #4
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2010-06-16T17:36:00+00:00
- Post Title: Problem with hex codes...

If you need the hex. value for those characters, then we can't probably can't help you if you just post the source of a program which doesn't handle those characters.

If those characters are displayed in the game, then just look what is the hex. value in an original file.
You can also try to guess hex. values in case the character may be in the game font, but is not used by the game.
Finally, if the character isn't in the game font, then you can try to add them to the font (usually using a generic graphics editor).

BTW, I don't know if you wrote this code, but to start I would recommend using a [Hashtable](http://java.sun.com/j2se/1.4.2/docs/api/java/util/Hashtable.html) or something similar instead of copy-pasting the same thing 4 times, and removing that empty exception catch block.
