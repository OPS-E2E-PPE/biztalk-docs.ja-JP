---
title: クラスター フェールオーバーのシナリオの構成のレビューと SQL Server のテスト |Microsoft Docs
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
ms.openlocfilehash: 981a879a5dad68bfb423a03b82e11fb646f912c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973259"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a>レビューとテスト フェールオーバーのシナリオに SQL Server クラスターの構成
Windows クラスタ リングと SQL Server を使用すると、1 つまたは複数の SQL Server インスタンスを「アクティブ」で実行されて、クラスターの各ノードのアクティブ/アクティブ モードで SQL Server を実行できます。 これは、ようにすると、たとえば、1 つのノードとその他のすべてのメッセージ ボックス データベースが[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]他のノード上のデータベース。 これにより、クラスターのハードウェア使用率を最大化することができます。  
  
 ただし、この構成を使用する場合、各ノードが SQL Server クラスター ノードのフェールオーバー中ですべての SQL Server インスタンスの負荷を処理できる同時にことを確認する必要があります。  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a>アクティブ/アクティブ クラスターのフェールオーバーを評価します。  
 1 つのノードが SQL Server クラスター ノードのフェールオーバーが発生した場合、すべての SQL Server インスタンスの負荷を処理できることを確認するときの考慮事項は次のとおりです。  
  
- フェールオーバー ノードには十分な CPU リソースがありますか。  
  
- フェールオーバー ノードに十分なメモリがあるでしょうか。  
  
- 十分なネットワーク帯域幅はありますか。  
  
- フェールオーバー ノードでより大きなディスク I/O の競合を処理できますか。  
  
  フェールオーバーをテストするときに、次のシナリオを評価する必要があります。  
  
- アクティブ サーバー上の電源障害  
  
- パッシブのサーバーで電源障害  
  
- ディスクの接続の切断  
  
- アクティブなノードでパブリック ネットワーク接続を解除  
  
- アクティブなノードでプライベート ネットワーク接続を解除  
  
- パッシブ ノードでパブリック ネットワーク接続を解除  
  
- パッシブ ノードでのプライベート ネットワーク接続の解除  
  
- 失敗した SQL Server サービス  
  
- 失敗した SQL Server エージェント サービス  
  
## <a name="using-an-activeactivepassive-cluster"></a>アクティブ/アクティブ/パッシブ クラスターの使用  
 1 つのノードはフェールオーバー シナリオでは、すべての SQL Server インスタンスを処理できないと判断した場合の代替では、アクティブ/アクティブ/パッシブのクラスタ リング モデルを使用します。 アクティブ/アクティブ/パッシブ クラスタ リング モデルでは、常にある 1 つのパッシブ ノードのフェールオーバーのシナリオに使用できる可能性が大幅に高まります。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: SQL Server の構成](~/technical-guides/checklist-configuring-sql-server.md)