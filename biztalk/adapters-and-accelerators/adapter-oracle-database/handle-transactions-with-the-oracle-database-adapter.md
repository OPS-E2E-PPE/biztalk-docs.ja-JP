---
title: Oracle データベース アダプターでトランザクションの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67d0cce0da65e1b2a7e3c1e6df1ef3eda944bbeb
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529182"
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a>Oracle データベース アダプターでトランザクションを処理します。
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] Oracle データベースで操作を実行中にトランザクションを開始しません。 代わりに、アダプターはアダプター クライアントによって提供されるトランザクション コンテキストを使用して、操作を実行します。 使用して、トランザクションで操作を実行するために、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、する必要があります。  
  
-   アダプター クライアントのトランザクションを有効にします。 たとえば、BizTalk Server のトランザクションを有効にする必要がありますを選択、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**WCF カスタム タブまたはWcf-oracledb ポートです。  
  
-   値を設定、 **UseAmbientTransaction**プロパティをバインド**True**アダプター。 バインディング プロパティの詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
> [!IMPORTANT]
>  アダプターを使用して、Oracle データベースでトランザクションを実行する、する必要がありますがインストールされている、 **Microsoft Transaction Server のサービスの Oracle**アダプターを実行するコンピューターで、Oracle クライアントをインストールするときに、コンポーネントクライアント。  
  
## <a name="transactions-in-the-outbound-operations"></a>送信操作のトランザクション  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]単一のトランザクションで送信操作を実行します。 複合操作は、のすべての操作を実行して、1 つのトランザクションが、異なる ODP.NET 接続を使用します。 送信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle のメタデータをどのようにですか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)します。  
  
## <a name="transactions-in-the-inbound-operations"></a>受信操作のトランザクション  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の 2 つの受信操作を公開します。  
  
- **ポーリング**:ポーリング ステートメントとポーリング後ステートメント (指定した) 場合は、一方、別のトランザクションでポーリング済みデータの使用可能なステートメントが実行されるトランザクションで実行されます。 同様に、ポーリング ステートメントとポーリング後ステートメントの実行同じ ODP.NET 接続を使用して一方、さまざまな ODP.NET 接続を使用してポーリング済みデータの使用可能なステートメントを実行します。  
  
- **通知**:通知の操作は、1 つの ODP.NET 接続を使用して、トランザクションで実行されます。  
  
  受信側に表示される操作の詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[アダプター画面 Oracle のメタデータをどのようにですか?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)