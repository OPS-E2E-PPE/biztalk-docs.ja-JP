---
title: "Wcf-customisolated アダプターとは何ですか。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fdf5a646f586030df6c9492fc6fb2999e49527a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-customisolated-adapter"></a>Wcf-customisolated アダプターとは何ですか。
WCF-CustomIsolated アダプタは、分離ホストを使用して、BizTalk Server における WCF 拡張機能コンポーネントの使用を有効にするために使用されます。 このアダプタによって、WCF フレームワークの完全な柔軟性が有効になります。 そのためユーザーは、受信場所の WCF バインドを選択して構成したり、エンドポイント動作やセキュリティ設定を指定したりできるようになります。 このアダプタを使用できるのは、インターネット インフォメーション サービス (IIS) でホストされているトランスポートのみです。  
  
 WCF-CustomIsolated アダプタは、1 つの受信アダプタのみで構成されています。 この WCF-CustomIsolated 受信アダプタは、分離ホストで実行されている受信場所に対して選択および構成した WCF バインド、サービス動作、エンドポイント動作、セキュリティ メカニズム、および受信メッセージ本文のソースを介して、WCF サービス要求を受信するために使用されます。 WCF-CustomIsolated 受信アダプタを使用する受信場所は、一方向または要求 - 応答 (双方向) として構成できます。  
  
 受信アダプターの WCF の詳細についてを参照してください[WCF アダプターとは?](../core/what-are-the-wcf-adapters.md)です。  
  
## <a name="see-also"></a>参照  
 [Wcf-customisolated アダプタを構成します。](../core/configuring-the-wcf-customisolated-adapter.md)   
 [WCF アダプタ](../core/wcf-adapters.md)