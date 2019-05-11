---
title: WCF アダプターの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- serializing, SOAP messages
- WCF adapters, extracting information
- messages, extracting information
- SOAP messages, serializing
- WCF adapters, message bodies
- send adapters, WCF adapters
- Web services, headers
- WCF adapters, send adapters
ms.assetid: 226a020a-2e12-41fe-a4a2-6683d9e98219
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc48f4da993c4e19c0053342c56b00deff16ead1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266250"
---
# <a name="wcf-send-adapter"></a>WCF 送信アダプタ
WCF 送信アダプタでは、型宣言不要なコントラクトを介して WCF サービスの呼び出しを行うことができます。  
  
## <a name="specifying-the-wcf-message-body"></a>WCF メッセージ本文の指定  
 BizTalk Server から送信する必要があるメッセージの本文は、次のオプションのいずれかを使用して、SOAP メッセージに挿入できます。  
  
- BizTalk メッセージ本文のコンテンツを抽出します。  
  
- テンプレートを使用してコンテンツを指定します。  
  
  送信ポート トランスポートのプロパティ ダイアログ ボックスで、これらのオプションを構成できます。  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a>BizTalk メッセージ本文のコンテンツを抽出します。  
 このオプションを選択すると、BizTalk メッセージ本文の内容は、送信 WCF メッセージ本文の SOAP Body 要素に挿入されます。  
  
#### <a name="specify-the-content-by-using-the-template"></a>テンプレートを使用してコンテンツを指定します。  
 このオプションを選択すると、BizTalk メッセージ本文は、送信 WCF メッセージ本文の指定された XML テンプレートでの SOAP body 要素に配置されます。  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a>BizTalk メッセージの SOAP メッセージにシリアル化  
 送信アダプターは、SOAP メッセージに BizTalk メッセージ送信する前にシリアル化します。メッセージのシリアル化中に、次の規則が適用されます。  
  
-   BizTalk メッセージがマルチパート メッセージの場合は、ボディ部のみが使用されます。  
  
-   BizTalk メッセージに SOAP エンベロープ全体が含まれている場合は、別の SOAP エンベロープにラップされます。  
  
-   BizTalk メッセージに任意の XML データが含まれている場合、BizTalk メッセージは SOAP 本文要素に配置されます。  
  
## <a name="handling-web-services-headers"></a>処理の Web サービス ヘッダー  
 BizTalk Server が送信操作中にコントロールを Web 経由でサービスの標準ヘッダー。 これらのヘッダーが設定され、WCF によって処理されます。 BizTalk Server アプリケーションによって変更可能な唯一の標準ヘッダーは、**を: アクション**ヘッダー。 場合、コンテキスト プロパティ**アクション**、WCF 送信アダプタは、プロパティの値を使用して設定するのには、アダプタの名前空間で指定されて、**アクション**SOAP メッセージにします。  
  
> [!NOTE]
>  動的送信ポート場合、**アクション**で指定された、 **OutboundHeaders**、コンテキスト プロパティを設定する、 **WCF です。アクション**は無視されます。  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a>BTS を指定します。IsDynamicSend コンテキスト プロパティ  
 WCF 送信アダプタでは、送信ポートの構成をキャッシュします。 場合、 **BTS します。IsDynamicSend**プロパティが true に、WCF 送信アダプターはキャッシュされた構成を使用しませんが、代わりにすべての構成情報メッセージから読み取り、送信メッセージのコンテキスト プロパティ。 静的送信ポートでは、WCF 送信アダプタが使用**BTS します。SPLastUpdatedTime**、これは、静的送信ポートの設定に最後に変更された、任意の構成があるかどうかを検出するために、静的に変更の送信ポート。 すべてのメッセージ コンテキストからすべての設定を読み取るには、このように、WCF 送信アダプターは必要はありません。  
  
 他にも、静的送信ポートのプロパティをオーバーライドするかどうか、 **WCF です。アクション**送信パイプラインのプロパティを設定する必要があります、 **BTS します。IsDynamicSend** true の場合でも、最終更新タイムスタンプは、WCF 送信アダプターにキャッシュされた構成は使用しないようにするプロパティが変更されていません。  
  
## <a name="see-also"></a>参照  
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 受信アダプター](../core/wcf-receive-adapter.md)   
 [WCF アダプターとは](../core/what-are-the-wcf-adapters.md)   
 [メッセージ コンテキスト プロパティを使用する方法](../core/how-to-use-message-context-properties.md)