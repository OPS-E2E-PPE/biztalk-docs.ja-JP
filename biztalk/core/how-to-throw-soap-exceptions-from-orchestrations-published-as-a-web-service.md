---
title: Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: d4ef3d975632b6230cf1e3df299d0d9455f39da0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255578"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a>Web サービスとして公開されたオーケストレーションから SOAP 例外をスローする方法
Web サービスとして公開されたオーケストレーションから SOAP 例外を返すことができます。 SOAP ポートにエラー メッセージを追加し、応答の代わりにそのエラー メッセージを送信します。  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a>Web サービスとして公開されたオーケストレーションから SOAP 例外をスローするには  
  
1.  SOAP ポートの種類にエラー メッセージを追加します。 エラー メッセージのメッセージの種類には、XML スキーマ (XSD) 準拠のスキーマや単純な文字列型を指定できます。  
  
    > [!NOTE]
    >  として文字列を返すため、 **SoapException**エラー情報が、エラー メッセージの種類として単純型の文字列を使用することができます。  
  
2.  オーケストレーションで、エラー メッセージを作成します。  
  
3.  使用して、**送信**図形をエラー メッセージに対応する SOAP ポートでのエラー操作にリンクします。 SOAP 例外は、返されたエラー メッセージをラップします。  
  
 オーケストレーションでエラーが返されない場合を使用して、異なる**送信**通常の応答操作を使用して標準の SOAP 応答メッセージを送信図形。  
  
## <a name="see-also"></a>参照  
 [エラー メッセージ](../core/fault-messages.md)   
 [Web サービスとしてのオーケストレーションの公開](../core/publishing-an-orchestration-as-a-web-service.md)