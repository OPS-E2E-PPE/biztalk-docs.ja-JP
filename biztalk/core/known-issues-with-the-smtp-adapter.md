---
title: "SMTP アダプターに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b530e39e-c4e7-4b98-be0b-4d02eb2e8dc7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8691da466c2915cee4b8746e20a0d5a96d82d81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-smtp-adapter"></a>SMTP アダプターに関する既知の問題
ここでは、エラー回避に役立つ情報を記載します。  
  
## <a name="known-issues"></a>既知の問題  
  
#### <a name="error-in-the-biztalk-server-application-log-if-emailbodytextcharset-is-not-defined"></a>EmailBodyTextCharset が定義されていない場合に BizTalk Server アプリケーション ログに記録されるエラー  
  
##### <a name="problem"></a>問題  
 EmailBodyTextCharset が定義されていない場合、BizTalk Server アプリケーション ログに次のようなエラーが生成されます。  
  
```  
Event Type:Error  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:5754  
Date:9/1/2006  
Time:10:50:11 AM  
User:N/A  
Computer:TEST2006  
Description:  
A message sent to adapter "SMTP" on send port "TIE Test_1.0.0.0_TIE_Test.TieRespTest_Email_Port_4f4f8f4101d5615a" with URI "mailto:approver@BTS2006.com" is suspended.   
Error details: Unknown Error Description   
MessageId: {3F12EBE1-1CDA-44FE-85FE-C2CB8228F287}  
InstanceID: {0616E750-22FF-4380-B413-C94718421340}  
```  
  
##### <a name="cause"></a>原因  
 値を設定する必要があります、 **EmailBodyTextCharset**パラメーター。  
  
##### <a name="resolution"></a>解決策  
 値を指定、 **EmailBodyTextCharset**パラメーター。  
  
## <a name="see-also"></a>参照  
 [SMTP アダプターのトラブルシューティング](../core/troubleshooting-the-smtp-adapter.md)