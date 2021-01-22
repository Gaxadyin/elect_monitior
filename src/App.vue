<template>
  <div id="app">
    <div class="fa">
      <h2>full-adder</h2>
      
      <div class="left">
        <div class="inp" @click="changeA()" :class="{ light: a, nolight: !a }">
          A:{{ a }}
        </div>
        <div class="inp" @click="changeB()" :class="{ light: b, nolight: !b }">
          B:{{ b }}
        </div>
        <div class="inp" @click="changeC()" :class="{ light: c, nolight: !c }" >
          C:{{ c }}
        </div>
      </div>
      <div class="box" @click="changeXOR1()" :class="{clicklight:click_xor1,noclicklight:!click_xor1}" style="margin-top:50px;margin-left:160px;">
        XOR
      </div>
      <div class="box" @click="changeXOR2()" :class="{clicklight:click_xor2,noclicklight:!click_xor2}" style="margin-top:90px;margin-left:320px;">
        XOR
      </div>
      <div class="box" @click="changeAND1()" :class="{clicklight:click_and1,noclicklight:!click_and1}" style="margin-top:210px;margin-left:320px;">
        AND
      </div>
      <div class="box" @click="changeAND2()" :class="{clicklight:click_and2,noclicklight:!click_and2}" style="margin-top:330px;margin-left:240px;">
        AND
      </div>
      <div class="box" @click="changeOR()" :class="{clicklight:click_or,noclicklight:!click_or}" style="margin-top:250px;margin-left:440px;">
        OR
      </div>
      <div class="resultbox"  style="margin-top:50px;margin-left:520px;">
        S:{{s}}
      </div>
      <div class="resultbox"  style="margin-top:200px;margin-left:520px;">
        C:{{ci}}
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011111" :control_heng_statu="line_a" :control_shu_statu="line_a" />
        <HelloWorld control_line="01100110" :control_heng_statu="line_a" :control_shu_statu="line_a" />
        <HelloWorld control_line="11111111" :control_heng_statu="line_b" :control_shu_statu="line_a" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_a" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_a" />
        <HelloWorld control_line="11111111" :control_heng_statu="line_c" :control_shu_statu="line_a" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_a" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_a" />
        <HelloWorld control_line="01110001" :control_heng_statu="line_a" :control_shu_statu="line_a" />

        
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line_a" control_shu_statu="False"/>
        <HelloWorld control_line="00010111" :control_heng_statu="line_b" :control_shu_statu="line_b" />
        <HelloWorld control_line="11101110" :control_heng_statu="line_b"   :control_shu_statu="line_b" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_b" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_b" />
        <HelloWorld control_line="11111111" :control_heng_statu="line_c" :control_shu_statu="line_b" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_b" />
        <HelloWorld control_line="01110001" :control_heng_statu="line_b" :control_shu_statu="line_b" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_a" control_shu_statu="False" />

        
      </div>
      <div class="left" >
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_c" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_b" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_a" control_shu_statu="False" />

      </div>
      <div class="left" >
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor1" control_shu_statu="False" />
        <HelloWorld control_line="00010111" :control_heng_statu="line_c" :control_shu_statu="line_c" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_c" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_c" />
        <HelloWorld control_line="11101000" :control_heng_statu="line_c" :control_shu_statu="line_c" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_b" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_a" control_shu_statu="False" />

      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011111" :control_heng_statu="line_xor1" :control_shu_statu="line_xor1"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line_c" :control_shu_statu="line_xor1" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_xor1" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_xor1" />
        <HelloWorld control_line="01110001" :control_heng_statu="line_xor1" :control_shu_statu="line_xor1" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor1" control_shu_statu="False"/>
        <HelloWorld control_line="10011111" :control_heng_statu="line_c" :control_shu_statu="line_c" />
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line_c" />
        <HelloWorld control_line="01110001" :control_heng_statu="line_c" :control_shu_statu="line_c" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor1" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_and2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_and2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_and1" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_and2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_and1" control_shu_statu="False" />
        <HelloWorld control_line="00010111" :control_heng_statu="line_and2" :control_shu_statu="line_and2" />
        <HelloWorld control_line="11101000" :control_heng_statu="line_and2" :control_shu_statu="line_and2" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line_xor2" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="10011001" :control_heng_statu="line_or" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False" />
      </div>
    </div>
    <div class="fa" >
      <h2 style="margin-bottom:200px;">adder</h2>
      <div class="adderbox" style="margin-top:360px;margin-left:230px" @click="changeA3()" :class="{ light: a3, nolight: !a3 }">A3:{{a3}}</div>
      <div class="adderbox" style="margin-top:360px;margin-left:390px" @click="changeA2()" :class="{ light: a2, nolight: !a2 }">A2:{{a2}}</div>
      <div class="adderbox" style="margin-top:360px;margin-left:550px" @click="changeA1()" :class="{ light: a1, nolight: !a1 }">A1:{{a1}}</div> 
      <div class="adderbox" style="margin-top:360px;margin-left:710px" @click="changeA0()" :class="{ light: a0, nolight: !a0 }">A0:{{a0}}</div>
      <div class="adderbox" style="margin-top:360px;margin-left:150px" @click="changeB3()" :class="{ light: b3, nolight: !b3 }">B3:{{b3}}</div>
      <div class="adderbox" style="margin-top:360px;margin-left:310px" @click="changeB2()" :class="{ light: b2, nolight: !b2 }">B2:{{b2}}</div>
      <div class="adderbox" style="margin-top:360px;margin-left:470px" @click="changeB1()" :class="{ light: b1, nolight: !b1 }">B1:{{b1}}</div>
      <div class="adderbox" style="margin-top:360px;margin-left:630px" @click="changeB0()" :class="{ light: b0, nolight: !b0 }">B0:{{b0}}</div> 
      <div class="adderbox" style="margin-top:270px;margin-left:860px" @click="changeM()"  :class="{ light: m, nolight: !m }">M:{{m}}</div> 
      <div class="ffa" style="margin-top:115px;margin-left:200px" :class="{clicklight:click2_fa1,noclicklight:!click2_fa1}" @click="changeFA1()">FA</div> 
      <div class="ffa" style="margin-top:115px;margin-left:350px" :class="{clicklight:click2_fa2,noclicklight:!click2_fa2}" @click="changeFA2()">FA</div> 
      <div class="ffa" style="margin-top:115px;margin-left:520px" :class="{clicklight:click2_fa3,noclicklight:!click2_fa3}" @click="changeFA3()">FA</div> 
      <div class="ffa" style="margin-top:115px;margin-left:680px" :class="{clicklight:click2_fa4,noclicklight:!click2_fa4}" @click="changeFA4()">FA</div> 
      <div class="ffa" style="margin-top:200px;margin-left:640px" :class="{clicklight:click2_xor4,noclicklight:!click2_xor4}" @click="change2XOR4()">XOR</div> 
      <div class="ffa" style="margin-top:200px;margin-left:480px" :class="{clicklight:click2_xor3,noclicklight:!click2_xor3}" @click="change2XOR3()">XOR</div> 
      <div class="ffa" style="margin-top:200px;margin-left:320px" :class="{clicklight:click2_xor2,noclicklight:!click2_xor2}" @click="change2XOR2()">XOR</div> 
      <div class="ffa" style="margin-top:200px;margin-left:160px" :class="{clicklight:click2_xor1,noclicklight:!click2_xor1}" @click="change2XOR1()">XOR</div> 
      <div class="ffa" style="margin-top:30px;margin-left:75px" :class="{clicklight:click2_xor5,noclicklight:!click2_xor5}" @click="change2XOR5()">XOR</div> 
      <div class="resultbox"  style="margin-top:-120px;margin-left:480px;font-size:30px;">
        S1:{{s1}}
      </div>
      <div class="resultbox"  style="margin-top:-120px;margin-left:640px;font-size:30px;">
        S0:{{s0}}
      </div>
      <div class="resultbox"  style="margin-top:-120px;margin-left:320px;font-size:30px;">
        S2:{{s2}}
      </div>
      <div class="resultbox"  style="margin-top:-120px;margin-left:160px;font-size:30px;">
        S3:{{s3}}
      </div>
      <div class="resultbox"  style="margin-top:-120px;margin-left:35px;font-size:30px;">
        溢出
      </div>
      <div class="left" >
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>

      </div>
      <div class="left" >
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>

      </div>
      <div class="left" >
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_xor5"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fac1"/>
        <HelloWorld control_line="01110001" :control_heng_statu="line2_fac1" :control_shu_statu="line2_fac1"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
 
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01110001" :control_heng_statu="line2_fac2" :control_shu_statu="line2_fac2"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac1" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>

      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac2" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac1" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b3"/>
      </div>
      <div class="left">
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa1"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa1"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_fac2" :control_shu_statu="line2_fa1"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_xor1"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="01110001" :control_heng_statu="line2_m" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <!-- 1 -->
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac2" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a3"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_a3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a3"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10001110" :control_heng_statu="line2_fac2" :control_shu_statu="line2_fac2"/>
        <HelloWorld control_line="11111001" :control_heng_statu="line2_fac2" :control_shu_statu="line2_fac2"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_m" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac2" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b2"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_b2"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b2"/>
      </div>
      <div class="left">
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa2"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa2"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa2"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_xor2"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="11111001" :control_heng_statu="line2_m" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a2"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a2"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a2"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_a2"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a2"/>
      </div>
      
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac3" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_m" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac3" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b1"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_b1"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b1"/>
      </div>
      <div class="left">
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa3"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa3"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_xor3"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="11111001" :control_heng_statu="line2_m" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a1"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a1"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a1"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_a1"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a1"/>
      </div>
      
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac4" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_m" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_fac4" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b0"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_b0"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_b0"/>
      </div>
      <div class="left">
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa4"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa4"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_fa4"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_xor4"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="11111001" :control_heng_statu="line2_m" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a0"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a0"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a0"/>
        <HelloWorld control_line="11111111" :control_heng_statu="line2_m" :control_shu_statu="line2_a0"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_a0"/>
      </div>
      
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_m" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_m" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10001110" :control_heng_statu="line2_m" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="01100110" control_heng_statu="False" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="11111001" :control_heng_statu="line2_m" :control_shu_statu="line2_m"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      <div class="left">
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
        <HelloWorld control_line="10011001" :control_heng_statu="line2_m" control_shu_statu="False"/>
        <HelloWorld control_line="00000000" control_heng_statu="False" control_shu_statu="False"/>
      </div>
      
    </div>

    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data() {
    return {
      a: 0,
      b: 0,
      c: 0,
      s:0,
      ci:0,
      click_xor1:false,
      click_xor2:false,
      click_and1:false,
      click_and2:false,
      click_or:false,
      line_a:'False',
      line_b:'False',
      line_c:'False',
      line_xor1:'False',
      line_xor2:'False',
      line_and1:'False',
      line_and2:'False',
      line_or:'False',

      a0:0,
      a1:0,
      a2:0,
      a3:0,
      b0:0,
      b1:0,
      b2:0,
      b3:0,
      m:0,
      s0:0,
      s1:0,
      s2:0,
      s3:0,
      line2_m:'False',
      line2_a0:'False',
      line2_a1:'False',
      line2_a2:'False',
      line2_a3:'False',
      line2_b0:'False',
      line2_b1:'False',
      line2_b2:'False',
      line2_b3:'False',
      line2_fa1:'False',
      line2_fa2:'False',
      line2_fa3:'False',
      line2_fa4:'False',
      line2_fac1:'False',
      line2_fac2:'False',
      line2_fac3:'False',
      line2_fac4:'False',
      line2_xor1:'False',
      line2_xor2:'False',
      line2_xor3:'False',
      line2_xor4:'False',
      line2_xor5:'False',

      click2_xor1:false,
      click2_xor2:false,
      click2_xor3:false,
      click2_xor4:false,
      click2_xor5:false,
      click2_fa1:false,
      click2_fa2:false,
      click2_fa3:false,
      click2_fa4:false,

    };
  },
  methods: {
    init(){
      this.s=0;
      this.ci=0;
      this.click_xor1=false;
      this.click_xor2=false;
      this.click_and1=false;
      this.click_and2=false;
      this.click_or=false;
      this.line_xor1='False';
      this.line_xor2='False';
      this.line_and1='False';
      this.line_and2='False';
      this.line_or='False';
    },
    init2(){
      this.s0=0;
      this.s1=0;
      this.s2=0;
      this.s3=0;
      this.line2_fa1='False';
      this.line2_fa2='False';
      this.line2_fa3='False';
      this.line2_fa4='False';
      this.line2_fac1='False';
      this.line2_fac2='False';
      this.line2_fac3='False';
      this.line2_fac4='False';
      this.line2_xor1='False';
      this.line2_xor2='False';
      this.line2_xor3='False';
      this.line2_xor4='False';
      this.line2_xor5='False';
      this.click2_xor1=false;
      this.click2_xor2=false;
      this.click2_xor3=false;
      this.click2_xor4=false;
      this.click2_xor5=false;
      this.click2_fa1=false;
      this.click2_fa2=false;
      this.click2_fa3=false;
      this.click2_fa4=false;
   },
    changeA() {
      this.init();
      if (this.a == 1) {
        this.a = 0;
        this.line_a = 'False';
      }
      else {
        this.a = 1;
        this.line_a= 'True';
      }
    },
    changeB() {
      this.init();
      if (this.b == 1) {
        this.b = 0;
        this.line_b='False';
      }
      else {
        this.b = 1;
        this.line_b='True';
      }
    },
    changeC() {
      this.init();
      if (this.c == 1) {
        this.c = 0;
        this.line_c = 'False';
      }
      else {
        this.c = 1;
        this.line_c = 'True';
      }
    },
    changeXOR1(){
      this.click_xor1 = true;
      if(this.line_a == this.line_b){
        this.line_xor1 = 'False';
      }else{
        this.line_xor1 = 'True';
      }
    },
    changeXOR2(){
      this.click_xor2 = true;
      if(this.line_xor1 == this.line_c){
        this.line_xor2 = 'False';
        this.s = 0;
      }else{
        this.line_xor2 = 'True';
        this.s=1;
      }
    },
    changeAND1(){
      this.click_and1 = true;
      if(this.line_c == 'True' && this.line_xor1=='True'){
        this.line_and1 = 'True';
      }else{
        this.line_and1 = 'False';
      }
    },
    changeAND2(){
      this.click_and2 = true;
      if(this.line_b == 'True' && this.line_a=='True'){
        this.line_and2 = 'True';
      }else{
        this.line_and2 = 'False';
      }
    },
    changeOR(){
      this.click_or = true;
      if(this.line_and2 == 'True' || this.line_and1 == 'True'){
        this.line_or = 'True';
        this.ci = 1;
      }else{
        this.line_or = 'False';
        this.ci = 0;
      }
    },
    changeA0(){
      this.init2();
      if (this.a0 == 1) {
        this.a0 = 0;
        this.line2_a0 = 'False';
      }
      else {
        this.a0 = 1;
        this.line2_a0= 'True';
      }
    },
    changeA1(){
      this.init2();
      if (this.a1 == 1) {
        this.a1 = 0;
        this.line2_a1 = 'False';
      }
      else {
        this.a1 = 1;
        this.line2_a1= 'True';
      }
    },
    changeA2(){
      this.init2();
      if (this.a2 == 1) {
        this.a2 = 0;
        this.line2_a2 = 'False';
      }
      else {
        this.a2 = 1;
        this.line2_a2= 'True';
      }
    },
    changeA3(){
      this.init2();
      if (this.a3 == 1) {
        this.a3 = 0;
        this.line2_a3 = 'False';
      }
      else {
        this.a3 = 1;
        this.line2_a3= 'True';
      }
    },
    changeB3(){
      this.init2();
      if (this.b3 == 1) {
        this.b3 = 0;
        this.line2_b3 = 'False';
      }
      else {
        this.b3 = 1;
        this.line2_b3= 'True';
      }
    },
    changeB0(){
      this.init2();
      if (this.b0 == 1) {
        this.b0 = 0;
        this.line2_b0 = 'False';
      }
      else {
        this.b0 = 1;
        this.line2_b0= 'True';
      }
    },
    changeB1(){
      this.init2();
      if (this.b1 == 1) {
        this.b1 = 0;
        this.line2_b1 = 'False';
      }
      else {
        this.b1 = 1;
        this.line2_b1= 'True';
      }
    },
    changeB2(){
      this.init2();
      if (this.b2 == 1) {
        this.b2 = 0;
        this.line2_b2 = 'False';
      }
      else {
        this.b2 = 1;
        this.line2_b2= 'True';
      }
    },
    changeM(){
      this.init2();
      if (this.m == 1) {
        this.m = 0;
        this.line2_m = 'False';
      }
      else {
        this.m = 1;
        this.line2_m= 'True';
      }
    },
    change2XOR1(){
      this.click2_xor1 = true;
      if (this.line2_b3 == this.line2_m) {
        this.line2_xor1 = 'False';
      }
      else {
        this.line2_xor1 = 'True';
      }
    },
    change2XOR2(){
      this.click2_xor2 = true;
      if (this.line2_b2 == this.line2_m) {
        this.line2_xor2 = 'False';
      }
      else {
        this.line2_xor2 = 'True';
      }
    },
    change2XOR3(){
      this.click2_xor3 = true;
      if (this.line2_b1 == this.line2_m) {
        this.line2_xor3 = 'False';
      }
      else {
        this.line2_xor3 = 'True';
      }
    },
    change2XOR4(){
      this.click2_xor4 = true;
      if (this.line2_b0 == this.line2_m) {
        this.line2_xor4 = 'False';
      }
      else {
        this.line2_xor4 = 'True';
      }
    },
    change2XOR5(){
      this.click2_xor5 = true;
      if (this.line2_fac1 == this.line2_fac2) {
        console.log(this.line2_fac1 == this.line2_fac2)
        this.line2_xor5 = 'False';

      }
      else {
        this.line2_xor5 = 'True';
      }
    },
    changeFA1(){
      this.click2_fa1 = true;
      let sum = 0;
      if(this.line2_xor1=="True"){
        sum+=1;
      }
      if(this.line2_a3=="True"){
        sum+=1;
      }
      if(this.line2_fac2=="True"){
        sum+=1;
      }
      switch(sum){
        case 0:{
          this.line2_fac1 = "False";
          this.line2_fa1 = "False";
          this.s3 = 0;
          break;
        }
        case 1:{
          this.line2_fac1 = "False";
          this.line2_fa1 = "True";
          this.s3 = 1;
          break;
        }
        case 2:{
          this.line2_fac1 = "True";
          this.line2_fa1 = "False";
          this.s3 = 0;
          break;
        }
        case 3:{
          this.line2_fac1 = "True";
          this.line2_fa1 = "True";
          this.s3 = 1;
          break;
        }
      }
    },
    changeFA2(){
      this.click2_fa2 = true;
      let sum = 0;
      if(this.line2_xor2=="True"){
        sum+=1;
      }
      if(this.line2_a2=="True"){
        sum+=1;
      }
      if(this.line2_fac3=="True"){
        sum+=1;
      }
      
      switch(sum){
        case 0:{
          this.line2_fac2 = "False";
          this.line2_fa2 = "False";
          this.s2 = 0;
          break;
        }
        case 1:{
          this.line2_fac2 = "False";
          this.line2_fa2 = "True";
          this.s2 = 1;
          break;
        }
        case 2:{
          this.line2_fac2 = "True";
          this.line2_fa2 = "False";
          this.s2 = 0;
          break;
        }
        case 3:{
          this.line2_fac2 = "True";
          this.line2_fa2 = "True";
          this.s2 = 1;
          break;
        }
      }
    },
    changeFA3(){
      this.click2_fa3 = true;
      let sum = 0;
      if(this.line2_xor3=="True"){
        sum+=1;
      }
      if(this.line2_a1=="True"){
        sum+=1;
      }
      if(this.line2_fac4=="True"){
        sum+=1;
      }
      
      switch(sum){
        case 0:{
          this.line2_fac3 = "False";
          this.line2_fa3 = "False";
          this.s1 = 0;
          break;
        }
        case 1:{
          this.line2_fac3 = "False";
          this.line2_fa3 = "True";
          this.s1 = 1;
          break;
        }
        case 2:{
          this.line2_fac3 = "True";
          this.line2_fa3 = "False";
          this.s1 = 0;
          break;
        }
        case 3:{
          this.line2_fac3 = "True";
          this.line2_fa3 = "True";
          this.s1 = 1;
          break;
        }
      }
    },
    changeFA4(){
      this.click2_fa4 = true;
      let sum = 0;
      if(this.line2_xor4=="True"){
        sum+=1;
      }
      if(this.line2_a0=="True"){
        sum+=1;
      }
      if(this.line2_m=="True"){
        sum+=1;
      }
      
      switch(sum){
        case 0:{
          this.line2_fac4 = "False";
          this.line2_fa4 = "False";
          this.s0 = 0;
          break;
        }
        case 1:{
          this.line2_fac4 = "False";
          this.line2_fa4 = "True";
          this.s0 = 1;
          break;
        }
        case 2:{
          this.line2_fac4 = "True";
          this.line2_fa4 = "False";
          this.s0 = 0;
          break;
        }
        case 3:{
          this.line2_fac4 = "True";
          this.line2_fa4 = "True";
          this.s0 = 1;
          break;
        }
      }
    },
  },
};
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.box {
  height: 60px;
  width: 60px;
  background-color: rgb(2, 92, 62);
  font-size: 20px;
  text-align: center;
  line-height: 60px;
  position: absolute;
  z-index: 10000;
  color: white;
  border-radius: 40%;
}
h2 {
  background: #eeeeee;
}
.fa {
  position: relative;
  height: 500px;
  width: 1500px;
  background-color: rgb(255, 255, 255);
  border-radius: 20px;
  border-width: 20px;
  border-color: rgb(180, 168, 168);
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  .left {
    float: left;
    .inp {
      height: 30px;
      width: 30px;
      background: white;
      padding: 30px;
      margin-bottom: 20px;
      font-size: 30px;
      border-radius: 20%;
      text-align: center;
      &:active {
        cursor: pointer;
         background: white;
        // transform: scale(1.1);
      }
    }
    .light {
      background: rgb(183, 238, 183);
    }
    .nolight {
      background: rgb(196, 85, 22);
    }
  }
}
.resultbox{
  height: 60px;
  width: 60px;
  padding: 30px;
  position: absolute;
  background: rgb(207, 207, 207);
  color: #000;
  font-size: 50px;
  border-radius: 20%;
  line-height: 60px;
  z-index: 969;
}

.adderbox{
  height: 60px;
  width: 60px;
  position: absolute;
  background: #c45516;
  line-height: 60px;
  font-size: 20px;
  border-radius: 20%;
  text-align: center;
  color: #000;
  z-index: 999;
  
}
.light {
    background: rgb(183, 238, 183);
}
.nolight {
  background: rgb(196, 85, 22);
}
.ffa{
  height: 50px;
  width: 90px;
  position: absolute;
  background: #a1f3b6;
  line-height: 50px;
  font-size: 20px;
  border-radius: 20px;
  text-align: center;
  color: white;
  z-index: 555;

}
.clicklight{
  background: rgb(4, 59, 4);
}
.noclicklight{
  background: rgb(183, 238, 183);
}
</style>>

