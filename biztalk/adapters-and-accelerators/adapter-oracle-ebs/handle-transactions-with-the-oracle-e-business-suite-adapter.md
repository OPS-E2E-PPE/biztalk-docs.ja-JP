---
title: Oracle E-business Suite アダプターでトランザクションを処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b443be9d-a93d-4836-8717-5ee9dad4442f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddfe7ebc56fce471bb4dceabf24c09e7a084bca1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375486"
---
# <a name="handle-transactions-with-the-oracle-e-business-suite-adapter"></a>Oracle E-business Suite アダプターでトランザクションを処理します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle E-business Suite の操作の実行中のトランザクションを開始しません。 代わりに、アダプターはアダプター クライアントによって提供されるトランザクション コンテキストを使用して、操作を実行します。 使用して、トランザクションで操作を実行するために、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]、する必要があります。  
  
-   アダプター クライアントのトランザクションを有効にします。 たとえば、BizTalk Server のトランザクションを有効にする必要がありますを選択、 **Use-transaction**  チェック ボックス、**トランザクション**の領域、**メッセージ**WCF カスタム タブまたはWcf-oracleebs ポートです。  
  
-   値を設定、 **UseAmbientTransaction**プロパティをバインド**True**アダプター。 バインディング プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
> [!IMPORTANT]
>  アダプターを使用して、Oracle E-business Suite でトランザクションを実行する、する必要がありますがインストールされている、 **Microsoft Transaction Server のサービスの Oracle**アダプターを実行するコンピューターで、Oracle クライアントをインストールするときに、コンポーネントクライアント。  
  
## <a name="transactions-in-the-outbound-operations"></a>送信操作のトランザクション  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]単一のトランザクションで送信操作を実行します。 複合操作は、のすべての操作を実行して、1 つのトランザクションが、異なる ODP.NET 接続を使用します。 送信側に表示される操作の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター画面 Oracle E-business Suite のメタデータをどのようにですか?](https://msdn.microsoft.com/library/dd788431.aspx)します。  
  
## <a name="transactions-in-the-inbound-operations"></a>受信操作のトランザクション  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]次の 2 つの受信操作を公開します。  
  
- **ポーリング**:ポーリング ステートメントとポーリング後ステートメント (指定した) 場合は、一方、別のトランザクションでポーリング済みデータの使用可能なステートメントが実行されるトランザクションで実行されます。 同様に、ポーリング ステートメントとポーリング後ステートメントの実行同じ ODP.NET 接続を使用して一方、さまざまな ODP.NET 接続を使用してポーリング済みデータの使用可能なステートメントを実行します。  
  
- **通知**:通知の操作は、1 つの ODP.NET 接続を使用して、トランザクションで実行されます。  
  
  受信側に表示される操作の詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[アダプター画面 Oracle E-business Suite のメタデータをどのようにですか?](https://msdn.microsoft.com/library/dd788431.aspx)します。  
  
## <a name="see-also"></a>参照  
[BizTalk Adapter for Oracle E-Business Suite について](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)