---
title: 確認して、SQL Server をテスト クラスターのフェールオーバーのシナリオの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e7bed17960700aee84631801e3e26cb05b25c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302218"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a>レビューし、テスト フェールオーバーのシナリオに SQL Server クラスターの構成
Windows クラスタ リングと SQL Server を使用すると、ここで、クラスターの各ノードは 1 つまたは複数の SQL Server インスタンスを"active"され実行されているアクティブ/アクティブ モードで SQL Server を実行できます。 これは、ようにすると、たとえば、1 つのノードとその他のすべてのメッセージ ボックス データベースに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のノード上のデータベースです。 これにより、クラスターのハードウェア使用率を最大化することができます。  
  
 ただし、この構成を使用する場合、各ノードが SQL Server クラスター ノードのフェールオーバー中ですべての SQL Server インスタンスの負荷を処理できる同時にことを確認する必要があります。  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a>アクティブ/アクティブ クラスターのフェールオーバーを評価します。  
 1 つのノードが SQL Server クラスター ノードのフェールオーバーが発生した場合、すべての SQL Server インスタンスの負荷を処理できることを確認する際の考慮事項は次のとおりです。  
  
-   フェールオーバー ノードに十分な CPU リソースがあるですか。  
  
-   フェールオーバー ノードに十分なメモリがあるですか。  
  
-   十分なネットワーク帯域幅はありますか。  
  
-   フェールオーバー ノードはより大きなディスク I/O の競合を処理できますか。  
  
 フェールオーバーをテストするときに、次のシナリオを評価する必要があります。  
  
-   アクティブ サーバー上の電源障害  
  
-   パッシブのサーバーに電源障害  
  
-   ディスクの接続の切断  
  
-   アクティブなノードでパブリック ネットワーク接続を解除  
  
-   アクティブなノードでプライベート ネットワーク接続を解除  
  
-   パッシブ ノードでパブリック ネットワーク接続を解除  
  
-   パッシブ ノードでプライベート ネットワーク接続を解除  
  
-   失敗した SQL Server サービス  
  
-   失敗した SQL Server エージェント サービス  
  
## <a name="using-an-activeactivepassive-cluster"></a>アクティブ/アクティブ/パッシブ クラスターを使用します。  
 1 つのノードのフェールオーバー シナリオですべての SQL Server インスタンスを処理できない場合は、代わりにでは、アクティブ/アクティブ/パッシブ クラスタ リング モデルを使用します。 アクティブ/アクティブ/パッシブ クラスタ リング モデルには、常にある 1 つのパッシブ ノードのフェールオーバー シナリオで使用可能な可能性が大幅に大きくなります。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: SQL Server を構成します。](~/technical-guides/checklist-configuring-sql-server.md)