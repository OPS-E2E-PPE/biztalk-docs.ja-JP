---
title: スケール アウトされた処理ホスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- hosts, processing
- hosts, high availability
- scaling, hosts
- hosts, planning
- hosts, scaling
- clustering
ms.assetid: c72ce8fc-7593-4700-8398-23d1a20515c3
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ee36777a5c64713fd31e86fe6ef2a1886b3348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269330"
---
# <a name="scaled-out-processing-hosts"></a>スケールアウトした処理ホスト
スケールアウトした処理ホストでは、オーケストレーション機能を 2 台以上のホスト コンピューターに分離することで、パフォーマンスの向上と高可用性を実現できます。 この分離により、複数のコンピューターを処理ホストに追加して冗長性を持たせることができます。 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の処理ホストは、各種ビジネス プロセスの調整を行うホスト インスタンスを 1 つ以上実行し、オーケストレーション用にプログラムで使用するオブジェクトのインスタンスを 1 つ作成します。  
  
 次の図は、処理ホストのインスタンスを実行する 2 台のコンピューターを使用して処理ホストの高可用性を実現した、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を示しています。 この図に示されている受信ホストおよび送信ホストの可用性は高くないことに注意してください。  
  
 ![スケール アウトされた処理ホスト](../core/media/tdi-ha-scaleprocess.gif "TDI_HA_ScaleProcess")  
  
 この構成では、処理ホストのインスタンスを個別に実行している 2 台の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターに、オーケストレーション処理の負荷が分散されます。 一方のコンピューターでエラーや障害が発生した場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、他方のコンピューターのホスト インスタンスを使用して残りのオーケストレーションを処理します。  
  
## <a name="maintaining-orchestration-state"></a>オーケストレーションの状態の保存  
 BizTalk Server では、オーケストレーションの状態が Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] で一元的に保存されます。ローカルの各 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターには保存されません。 メッセージ ボックス データベースの状態を保存することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、単一の処理ホスト インスタンスに依存することなく、どの処理ホスト インスタンスでもオーケストレーションを処理できるようになります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のオーケストレーション処理中にエラーが発生した場合、同じ処理ホストの別のインスタンスが、最後に保存した状態からオーケストレーションを処理できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性](../core/providing-high-availability-for-biztalk-hosts.md)