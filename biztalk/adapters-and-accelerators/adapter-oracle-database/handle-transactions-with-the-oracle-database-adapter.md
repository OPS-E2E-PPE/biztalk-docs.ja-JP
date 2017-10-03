---
title: "Oracle データベース アダプターでトランザクションの処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d45355100e728220745620e1c0df3552f523f649
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a>Oracle データベース アダプターでトランザクションを処理します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]Oracle データベースで操作を実行中のトランザクションを開始しません。 代わりに、アダプターは、アダプターのクライアントによって提供されるトランザクション コンテキストを使用して操作を実行します。 使用してトランザクションで操作を実行するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、する必要があります。  
  
-   アダプターのクライアントのトランザクションを有効にします。 例については、トランザクションを有効にする[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]を選択する必要があります、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**タブに移動して、Wcf-custom または Wcf-oracledb ポートです。  
  
-   値を設定、 **UseAmbientTransaction**にプロパティのバインド**True**アダプターでします。 バインディング プロパティの詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
> [!IMPORTANT]
>  トランザクションを実行する Oracle データベースで、アダプターを使用するインストール必要がありますが、 **Microsoft Transaction Server のサービスの Oracle**コンポーネント、アダプターを実行しているコンピューターで、Oracle クライアントをインストールするときに、クライアントです。  
  
## <a name="transactions-in-the-outbound-operations"></a>送信操作のトランザクション  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]単一のトランザクションで送信操作を実行します。 複合操作は、すべての操作を実行して、1 つのトランザクションではなく異なる ODP.NET 接続を使用します。 送信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle メタデータをどのように?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)です。  
  
## <a name="transactions-in-the-inbound-operations"></a>受信操作のトランザクション  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つの受信操作を公開します。  
  
-   **ポーリング**: ポーリング ステートメントおよび (指定した場合)、ポーリング後ステートメントが実行されるトランザクションでは、一方、別のトランザクションでポーリングされたデータの使用可能なステートメントを実行します。 同様に、ポーリング ステートメントとポーリング後ステートメントは、実行同じ ODP.NET 接続を使用して一方、ODP.NET は別の接続を使用してポーリングされたデータの使用可能なステートメントを実行します。  
  
-   **通知**: 通知操作は 1 つの ODP.NET 接続を使用して、トランザクションで実行します。  
  
 受信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle メタデータをどのようにしますか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)