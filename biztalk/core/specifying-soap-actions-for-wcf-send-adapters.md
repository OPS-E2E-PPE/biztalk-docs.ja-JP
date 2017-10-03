---
title: "SOAP アクションの指定の WCF 送信アダプタ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385e92f7801dc2512fbd038bd0b005d95c503e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a>WCF 送信アダプタ用の SOAP アクションの指定
設定することができます、 **WCF です。アクション**WCF 送信アダプタのトランスポートのプロパティ ダイアログ ボックスまたはオーケストレーションのコンテキスト プロパティ**式**図形です。 設定した場合、 **WCF です。アクション**オーケストレーションのコンテキスト プロパティのままにする必要があります、**アクション**静的送信ポートの WCF アダプター トランスポートのプロパティ ダイアログ ボックスでフィールドを空白。 また、静的送信ポートでアクションを指定する場合、 **WCF です。アクション**オーケストレーションで設定したコンテキスト プロパティは上書きされます。  
  
 さらは、このプロパティを指定する 2 つの方法があります。 シングル アクション形式とアクション マッピング形式です。 このプロパティをシングル アクション形式で指定した場合 (http://MyService/IMyContract/MyAction1 など)、送信メッセージについて WCF 送信アダプタのトランスポートのプロパティを設定するダイアログ ボックスの SOAP アクションは、常にこのプロパティで指定した値に設定されます。 オーケストレーションでシングル アクション形式を設定する代わりに、**式**図形です。 例を次に示します。  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 によって送信される SOAP アクションを決定をアクション マッピング形式でこのプロパティを設定する場合、 **BTS です。操作**コンテキスト プロパティです。 たとえば、このプロパティは、WCF では、次の XML 形式に設定されている場合は、送信アダプター トランスポートのプロパティ ダイアログ ボックスおよび**BTS です。操作**プロパティに設定されている**Operation_1**オーケストレーションの送信ポートで、WCF 送信アダプタは送信 SOAP アクションの http://MyService/IMyContract/MyAction1 を使用します。  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 アクション マッピングを指定**WCF です。アクション**で、**式**図形はサポートされていません。 アクション マッピングの指定は、[WCF トランスポートのプロパティ] ダイアログ ボックスで行う必要があります。 使用して、WCF アダプターが SOAP アクションを検索し、 **BTS です。操作**コンテキスト プロパティは、オーケストレーションは、メッセージは送信ポートでの操作の名前に設定します。  
  
 送信メッセージが、コンテンツ ベースのルーティング (CBR) にルーティングされる場合、 **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**プロパティが設定されていない、WCF 送信アダプタは全体のアクションのマッピングを設定送信 WCF メッセージのアクションへの文字列。 この問題を回避するには、次のいずれかの操作を行います。  
  
-   送信ポートのアクション フィールドを http://MyService/IMyContract/MyAction1 に設定します。  
  
-   設定、 **BTS です。操作**パイプラインのコンテキスト プロパティです。 たとえばの値を設定**http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation**を Operation1 にします。  
  
-   アクション フィールドを空白のままにして、受信メッセージのアクションを使用します。  
  
 BizTalk WCF サービス使用ウィザードを使用して、シングル アクションまたはアクション マッピングで WCF サービスを使用 (消費) することもできます。 詳細については、次を参照してください。 [BizTalk WCF サービス使用ウィザードを使用して WCF サービスを使用する方法](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF アダプター コンテキスト プロパティを使用して動的送信ポートの構成](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)