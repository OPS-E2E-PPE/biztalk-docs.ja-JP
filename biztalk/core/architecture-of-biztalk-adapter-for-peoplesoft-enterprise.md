---
title: BizTalk Adapter for PeopleSoft Enterprise のアーキテクチャ |Microsoft ドキュメント
description: メッセージを受信する方法について説明します、メッセージがどのように検証すると、BizTalk Server で、PeopleSoft アダプターを使用する場合は、コンポーネント インターフェイス メソッドの情報を提供
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
ms.openlocfilehash: 3eb0f43dacdbd6036ef59fa3fe16102d4fe12379
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013697"
---
# <a name="peoplesoft-enterprise-adapter-architecture"></a>PeopleSoft Enterprise アダプターのアーキテクチャ
Microsoft BizTalk Adapter for PeopleSoft Enterprise は、基本的な操作の実行中に BizTalk Server から XML メッセージを受信します。 この XML メッセージは SOAP エンベロープに埋め込まれます。 BizTalk Adapter for PeopleSoft Enterprise は、SOAP 要求をサーバーに転送します。 このアダプターは、Jolt トランザクション プロトコルによって PeopleSoft システムに接続する PeopleSoft psjoa クラスを使用して、PeopleSoft システムと通信します。 PeopleSoft システムは、要求を受信して、ビジネス ロジックを実行します。 応答は、同様のプロセスによって戻されます。  
  
 ![](../core/media/psadapter-01-architecture.gif "PSAdapter_01_Architecture")  

  
## <a name="component-interface-methods"></a>コンポーネント インターフェイス メソッド  
 PeopleSoft コンポーネント インターフェイスに提供されている基本 API は、本質的に低レベルです。 クライアントは、これらの API について複数の呼び出しを要求します。 たとえば、コンポーネント インターフェイスのインスタンスのプロパティを取得する場合、クライアントは低レベルの Get メソッドを呼び出した後、1 つ以上の呼び出しによってキーの値を設定する必要があります。 さらに、プロパティを取得するには、複数の呼び出しを送信する必要があります。 BizTalk Adapter for PeopleSoft Enterprise を使用すると、標準メソッド (Get、Create、Find、Update) の新しいセットが提供されるので、クライアントは 1 回の呼び出しを行うだけで同じ結果を得ることができます。 つまり、BizTalk Adapter for PeopleSoft Enterprise がクライアントの代わりに複数の呼び出しを実行することになります。 メソッドの詳細については、次を参照してください。[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)です。  
  
 PeopleSoft のスキーマを作成するには、BizTalk Adapter for PeopleSoft Enterprise で PeopleSoft コンポーネント インターフェイスの定義またはメタデータを取得します。  
  
 BizTalk Adapter for PeopleSoft Enterprise の送信機能はコンポーネント インターフェイスに基づいているので、PeopleSoft Integration Broker は不要です。 コンポーネント インターフェイスは Web サービスとして公開され、BizTalk Server からアクセスできます。  
  
### <a name="validation"></a>検証  
 BizTalk Adapter for PeopleSoft Enterprise では、BizTalk Server から XML メッセージを受信すると、2 レベルの検証が実行されます。  
  
-   XML メッセージが XML 仕様に関して有効である必要があります。  
  
-   XML メッセージが、特定の Web サービスによる要求と一致している必要があります (たとえば、データ型などのインターフェイスの一致)。  
  
> [!NOTE]
>  ビジネス ロジックに関する検証は実行されません。これは PeopleSoft システムのドメインなので、BizTalk Adapter for PeopleSoft Enterprise に対して透過的だからです。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-peoplesoft-enterprise.md)   