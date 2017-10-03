---
title: "WCF-Custom アダプタについて | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e090f82bc43d96dc14295af2fac2807cf1fd137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-custom-adapter"></a>WCF-Custom アダプタについて
WCF-Custom アダプタを使用すると、BizTalk Server で WCF 拡張機能コンポーネントを使用できるようになります。 このアダプタによって、WCF フレームワークの完全な柔軟性が有効になります。 これにより、ユーザーが、受信場所や送信ポートの WCF バインドを選択して構成できるようになります。 また、エンドポイント動作やセキュリティ設定を指定することもできます。  
  
 WCF-Custom アダプタは、2 つのアダプタ (受信アダプタと送信アダプタ) で構成されます。  
  
 **Wcf-custom 受信アダプター**  
  
 この WCF-Custom 受信アダプタは、受信場所の [トランスポートのプロパティ] ダイアログ ボックスで選択および構成したバインド、サービス動作、エンドポイント動作、セキュリティ メカニズム、および受信メッセージ本文のソースを使用して WCF サービス要求を受信するために使用されます。 WCF-Custom 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。  
  
 **Wcf-custom 送信アダプタ**  
  
 この WCF-Custom 受信アダプタは、型宣言が不要なコントラクトと、選択および構成したバインド、サービス動作、エンドポイント動作、セキュリティ メカニズム、および送信メッセージ本文のソースを使用して WCF サービスを呼び出すために使用されます。  
  
 WCF の詳細については、受信し送信アダプターを参照してください[WCF アダプタは何ですか?](../core/what-are-the-wcf-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF カスタム アダプターを構成します。](../core/configuring-the-wcf-custom-adapter.md)   
 [WCF アダプタ](../core/wcf-adapters.md)