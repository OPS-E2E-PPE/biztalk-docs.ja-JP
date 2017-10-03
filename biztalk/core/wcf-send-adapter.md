---
title: "WCF 送信アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70604fbc15f5f15b0a7ff2325debdc28ac3a97c1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-send-adapter"></a>WCF 送信アダプタ
WCF 送信アダプタでは、型宣言が不要なコントラクトを使用して WCF サービスを呼び出すことができます。  
  
## <a name="specifying-the-wcf-message-body"></a>WCF メッセージ本文の指定  
 BizTalk Server から送信する必要があるメッセージ本文は、次のオプションのいずれかを使用して、SOAP メッセージに挿入することができます。  
  
-   Extract the content of the BizTalk message body (BizTalk メッセージ本文の内容を抽出)  
  
-   Specify the content by using the template (テンプレートを使用して内容を指定)  
  
 送信ポートのトランスポート プロパティ ダイアログ ボックスで、これらのオプションを構成できます。  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a>Extract the Content of the BizTalk Message Body (BizTalk メッセージ本文の内容を抽出)  
 このオプションを選択すると、BizTalk メッセージ本文の内容が、送信 WCF メッセージ本文の SOAP Body 要素に挿入されます。  
  
#### <a name="specify-the-content-by-using-the-template"></a>Specify the Content by Using the Template (テンプレートを使用して内容を指定)  
 このオプションを選択すると、BizTalk メッセージ本文が、送信 WCF メッセージ本文の指定された XML テンプレートの下にある SOAP Body 要素に配置されます。  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a>BizTalk メッセージの SOAP メッセージへのシリアル化  
 送信アダプタは、BizTalk メッセージを送信する前に SOAP メッセージにシリアル化します。メッセージのシリアル化中に、次の規則が適用されます。  
  
-   BizTalk メッセージがマルチパート メッセージの場合、ボディ部のみが使用されます。  
  
-   BizTalk メッセージに SOAP エンベロープ全体が含まれる場合は、別の SOAP エンベロープにラップされます。  
  
-   BizTalk メッセージに任意の XML データが含まれている場合、BizTalk メッセージは SOAP 本文要素に配置されます。  
  
## <a name="handling-web-services-headers"></a>Web サービス ヘッダーの処理  
 送信操作中、BizTalk Server は Web サービスの標準ヘッダーを制御できません。 これらのヘッダーは、WCF によって設定され、処理されます。 BizTalk Server アプリケーションによって変更できる唯一の標準ヘッダーは、 **、: アクション**ヘッダー。 場合、コンテキスト プロパティ**アクション**、WCF 送信アダプタを設定するプロパティの値を使用して、アダプターの名前空間が指定されて、**アクション**SOAP メッセージにします。  
  
> [!NOTE]
>  動的送信ポート場合、**アクション**で指定された、 **OutboundHeaders**、コンテキスト プロパティを設定する、 **WCF です。アクション**は無視されます。  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a>BTS.IsDynamicSend コンテキスト プロパティの指定  
 WCF 送信アダプタは、送信ポートの構成をキャッシュします。 場合、 **BTS です。IsDynamicSend**プロパティが true に、WCF 送信アダプタはキャッシュされた構成を使用しませんが、代わりにすべての構成情報メッセージから読み取り、送信メッセージのコンテキスト プロパティです。 静的送信ポートで、WCF 送信アダプタで使用**BTS です。SPLastUpdatedTime**、最終変更時刻を静的送信ポートの設定は、任意の構成があるかどうかを検出するために、静的な 変更の送信ポート。 この方法では、WCF 送信アダプタは、すべてのメッセージ コンテキストからのすべての設定を読み取る必要はありません。  
  
 以外の場合、静的送信ポートのプロパティをオーバーライドするかどうか、 **WCF です。アクション**送信パイプラインのプロパティを設定する必要があります、 **BTS です。IsDynamicSend**真の場合でも、最終更新タイムスタンプは、WCF 送信アダプターにキャッシュされた構成は使用しないようにするプロパティが変更されていません。  
  
## <a name="see-also"></a>参照  
 [WCF アダプタのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 受信アダプター](../core/wcf-receive-adapter.md)   
 [WCF アダプタは?](../core/what-are-the-wcf-adapters.md)   
 [メッセージ コンテキスト プロパティを使用する方法](../core/how-to-use-message-context-properties.md)