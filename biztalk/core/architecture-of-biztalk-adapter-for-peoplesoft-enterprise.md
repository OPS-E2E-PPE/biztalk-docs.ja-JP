---
title: BizTalk Adapter for PeopleSoft Enterprise のアーキテクチャ |Microsoft Docs
description: メッセージを受信する方法について説明しますと、メッセージは、方法が検証され、BizTalk Server で、PeopleSoft アダプターを使用する場合は、コンポーネント インターフェイスのメソッドで情報を提供します
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f246e974-a082-430c-ad15-23a5e597738b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d65bfed5d76d4cb78a476ee56c863247a92a7ae
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528808"
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a>PeopleSoft Enterprise アダプターのアーキテクチャ
基本の操作中に Microsoft BizTalk Adapter for PeopleSoft Enterprise、アダプターは BizTalk Server から XML メッセージを受信します。 SOAP エンベロープで XML メッセージを囲みます。 BizTalk Adapter for PeopleSoft Enterprise では、サーバーに SOAP 要求を転送します。 アダプターは、Jolt トランザクション プロトコルによって PeopleSoft システムに接続する PeopleSoft psjoa クラスを使用して PeopleSoft システムと通信します。 PeopleSoft システムでは、要求を受信し、ビジネス ロジックを実行します。 同様のプロセスを遡って、応答が送信されます。  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  

  
## <a name="component-interface-methods"></a>コンポーネント インターフェイス メソッド  
 PeopleSoft コンポーネント インターフェイスで提供される基本的な Api は、本質的に低レベルです。 クライアントでは、これらの Api の複数の呼び出しが必要です。 たとえば、コンポーネント インターフェイスのインスタンスのプロパティを取得する、クライアントでは、低レベルの Get メソッドの呼び出し後にキー値を設定する 1 つまたは複数の呼び出しに必要です。 プロパティを取得する複数の呼び出しに送信する必要があります。 BizTalk Adapter for PeopleSoft Enterprise では、標準的なメソッド (Get、作成、検索、および更新) の新しいセットは、クライアントが、同じ結果を 1 回の呼び出しに必要であるような方法で提供されます。 これは BizTalk Adapter for PeopleSoft Enterprise がクライアントの代わりに複数の呼び出しを実行することで行います。 メソッドの詳細については、次を参照してください[付録 a:。コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)します。  
  
 PeopleSoft のスキーマを作成するには、BizTalk Adapter for PeopleSoft Enterprise は PeopleSoft コンポーネント インターフェイスの定義またはメタデータを取得します。  
  
 BizTalk Adapter for PeopleSoft Enterprise では、送信機能はコンポーネント インターフェイスに基づいており、PeopleSoft Integration Broker は必要ありません。 コンポーネントのインターフェイスは、BizTalk Server からアクセスできるは、Web サービスとして公開されます。  
  
### <a name="validation"></a>検証  
 BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server から XML メッセージを受信、2 つのレベルの検証が実行されます。  
  
-   XML メッセージは、XML 仕様に関して有効である必要があります。  
  
-   XML メッセージでは、特定の Web サービス (たとえば、インターフェイスなどのデータ型の一致) で必要なものと一致する必要があります。  
  
> [!NOTE]
>  PeopleSoft システムのドメインと BizTalk Adapter for PeopleSoft Enterprise に対して透過的ですが、ビジネス ロジックに関する検証は行われません。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   