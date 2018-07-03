---
title: Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328f468485f729df03c28bca48a8b5ed4eaf59e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015203"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法
Web サービスとして公開されたオーケストレーションから SOAP 例外を返すことができます。 SOAP ポートにエラー メッセージを追加し、応答の代わりにそのエラー メッセージを送信します。  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>Web サービスとして公開されたオーケストレーションから SOAP 例外をスローするには  
  
1. SOAP ポートの種類にエラー メッセージを追加します。 エラー メッセージのメッセージの種類には、XML スキーマ (XSD) 準拠のスキーマや単純な文字列型を指定できます。  
  
   > [!NOTE]
   >  として文字列を返す、 **SoapException**エラー情報と共にエラー メッセージの種類として単純型の文字列を使用することができます。  
  
2. オーケストレーションで、エラー メッセージを作成します。  
  
3. 使用して、**送信**図形をエラー メッセージに対応する SOAP ポートでのエラー操作にリンクします。 SOAP 例外は、返されたエラー メッセージをラップします。  
  
   オーケストレーションがエラーを返さない場合を使用して、さまざまな**送信**図形を通常の応答の操作を使用して標準の SOAP 応答メッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [エラー メッセージ](../core/fault-messages.md)   
 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)