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
ms.openlocfilehash: 12c849d592a7cdce5968678f524ec15562830eba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333802"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法
Web サービスとして発行したオーケストレーションから SOAP 例外を返すことができます。 SOAP ポートにエラー メッセージを追加し、応答ではなく、エラー メッセージを送信します。  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>Web サービスとして公開されたオーケストレーションから SOAP 例外をスローするには  
  
1. SOAP ポートの種類には、エラー メッセージを追加します。 エラー メッセージのメッセージの種類には、任意の XML スキーマ (XSD) 準拠のスキーマまたは単純型を指定できます。  
  
   > [!NOTE]
   >  として文字列を返す、 **SoapException**エラー情報と共にエラー メッセージの種類として単純型の文字列を使用することができます。  
  
2. オーケストレーションでは、エラー メッセージを作成します。  
  
3. 使用して、**送信**図形をエラー メッセージに対応する SOAP ポートでのエラー操作にリンクします。 SOAP 例外は、返されたエラー メッセージをラップします。  
  
   オーケストレーションがエラーを返さない場合を使用して、さまざまな**送信**図形を通常の応答の操作を使用して標準の SOAP 応答メッセージを送信します。  
  
## <a name="see-also"></a>参照  
 [エラー メッセージ](../core/fault-messages.md)   
 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)