---
title: 送信アダプターの wcf SOAP アクションの指定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47781b2b8add675207136248b38b0dadfe6b5610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023496"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a>WCF 送信アダプタ用の SOAP アクションの指定
設定することができます、 **WCF です。アクション**WCF 送信アダプターのトランスポートのプロパティ ダイアログ ボックスまたはオーケストレーションのコンテキスト プロパティ**式**図形。 設定した場合、 **WCF です。アクション**オーケストレーションのコンテキスト プロパティのままにする必要があります、**アクション**静的送信ポートの WCF アダプター トランスポートのプロパティ ダイアログ ボックスでフィールドを空白。 また、静的送信ポートでアクションを指定した場合、 **WCF です。アクション**オーケストレーションで設定したコンテキスト プロパティは上書きされます。  
  
 さらは、このプロパティを指定する 2 つの方法があります。 シングル アクション形式とアクション マッピング形式。 シングル アクション形式では、このプロパティを設定するかどうか: たとえば、 http://MyService/IMyContract/MyAction1: wcf SOAP アクションの送信アダプター トランスポートのプロパティ ダイアログ ボックスは、送信メッセージは、このプロパティで指定された値に設定されて常にします。 オーケストレーションで、シングル アクション形式を設定する代わりに、**式**図形。 例を次に示します。  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 によって送信される SOAP アクションを決定アクション マッピング形式でこのプロパティを設定する場合、 **BTS します。操作**コンテキスト プロパティ。 たとえば、このプロパティは、WCF では、次の XML 形式に設定されている場合は、送信アダプター トランスポートのプロパティ ダイアログ ボックスおよび**BTS します。操作**プロパティに設定されて**Operation_1**オーケストレーションの送信ポートの WCF 送信アダプタが使用 http://MyService/IMyContract/MyAction1 送信 SOAP アクション。  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 アクション マッピングを指定**WCF です。アクション**で、**式**図形がサポートされていません。 アクション マッピングの指定は、[WCF トランスポートのプロパティ] ダイアログ ボックスで行う必要があります。 WCF アダプターが SOAP アクションを使用して検索し、 **BTS します。操作**コンテキスト プロパティは、オーケストレーションは、メッセージは送信ポートでの操作の名前に設定します。  
  
 送信メッセージが、ルーティング コンテンツ ベースのルーティング (CBR) のかどうか、 **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**プロパティが設定されていない、WCF 送信アダプタは、アクション マッピング文字列全体を送信 WCF メッセージのアクションに設定します。 この問題を回避するには、次のいずれかの操作を行います。  
  
- アクション フィールドを設定する送信ポートでhttp://MyService/IMyContract/MyAction1します。  
  
- 設定、 **BTS します。操作**パイプラインのコンテキスト プロパティ。 たとえばの値を設定**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**を Operation1 にします。  
  
- アクション フィールドを空白のままにして、受信メッセージのアクションを使用します。  
  
  BizTalk WCF サービス使用ウィザードを使用して、シングル アクションまたはアクション マッピングで WCF サービスを使用 (消費) することもできます。 詳細については、次を参照してください。 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)します。  
  
## <a name="see-also"></a>参照  
 [WCF アダプター コンテキスト プロパティによる動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)