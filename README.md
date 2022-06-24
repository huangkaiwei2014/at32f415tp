# at32f415tp
at32f415tp
//if ( TIM_GetITStatus( TIM3, TIM_IT_CC3 ) == SET )
// {
//  TIM_ClearFlag( TIM3, TIM_IT_CC3 );
//  IR_Up = 0;
//  IR_ThisPluse = TIM_GetCapture3( TIM3 );
//  
//  if ( IR_ThisPluse > IR_LastPluse )
//  {
//   IR_PluseSub = IR_ThisPluse - IR_LastPluse;
//  }
//  else {
//   IR_PluseSub = 0xffff - IR_LastPluse + IR_ThisPluse;
//  }
//  
//  IR_LastPluse = IR_ThisPluse;
//  IR_PluseCnt++;
//  
//  if ( IR_PluseCnt == 2 )
//  {
//   if (( IR_PluseSub > 5000 ) && ( IR_PluseSub < 8000 ))
//   {
//    IR_Sta = 0x01;
//   }
//  }
//  else if ( IR_Sta & 0x01 ) //如果引导成功开始解码
//  {
//   if (( IR_PluseSub < 450 ) || ( IR_PluseSub > 1300 ))
//   {
//    IR_Sta          = 0;
//    IR_PluseCnt  = 0;
//    IR_Code       = 0;
//   }
//   else
//   {
//    IR_Code <<= 1;
//    if (( IR_PluseSub > 900 ) && ( IR_PluseSub < 1300 ))
//    {
//     IR_Code |= 0x01;
//    }
//    if ( IR_PluseCnt == 34 )
//    {
//     IR_Key = IR_Code;
//		 User_Key=IR_Code;
//     IR_Sta = 0x02;
//     printf( "IR Down is : 0x%8x\n\n", IR_Key );
//    }
//   }
//  }
//  else if ( IR_Sta & 0x02 )
//  {
//   switch ( IR_PluseCnt )
//   {
//    case 35:
//    {
//     if ( ( IR_PluseSub < 4500 ) || ( IR_PluseSub > 7000 ) )
//     {
//      IR_PluseCnt--;
//     }
//     break;
//    }
//    case 36:
//    {
//     IR_PluseCnt = 34;
//     if ( ( IR_PluseSub > 45000) && ( IR_PluseSub < 60000 ) )
//     { 
//      IR_Key = IR_Code;
//			User_Key=IR_Code;
//      printf( "IR continue is : 0x%8x\n\n", IR_Key );
//     }
//     break;
//    }
//   }
//  }
// }
// 
// if ( TIM_GetITStatus( TIM3, TIM_IT_Update ) == SET )
//	 {
//		TIM_ClearFlag( TIM3, TIM_IT_Update ); 
//		if ( GPIO_ReadInputDataBit( GPIOB, GPIO_Pin_0 ) == SET )
//		{
//		 IR_Up++;
//		 if ( IR_Up >= 2 )
//		 {
//			IR_Code     = 0;
//			IR_Sta      = 0;
//			IR_PluseCnt = 0;
//		 }
//		}
//	 } 
