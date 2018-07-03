---
title: 仮想化環境の Hyper-v の概要に、BizTalk Server ソリューションを展開する潜在的な利点があります |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 588c70f0-68f0-4e58-8f3d-aa6834397bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c88a8dcc6386b6030d4ca429010b6db1acfb81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024448"
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a>仮想化環境の Hyper-v の概要に、BizTalk Server ソリューションを展開する潜在的な利点があります。
このトピックでは、デプロイの利点をいくつかについて説明します、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想化環境にソリューション。  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a>仮想環境に Hyper V 上の BizTalk Server ソリューションの実行の利点があります。  
 HYPER-V 仮想化環境で実行する BizTalk Server ソリューションを展開するには、次のような柔軟性と機能が実現されます。  
  
- **1 台の物理コンピューターの複数の個別の論理セキュリティ境界を定義する機能**HYPER-V は別々 の論理セキュリティの境界、または 1 つの物理ハードウェア リソース内のパーティションの作成に対応します。 パーティションは、オペレーティング システムが実行される、ハイパーバイザーでサポートされる分離の 1 つの論理単位です。 たとえば、インストール時にこれをすることはできませんが、1 台の HYPER-V ホスト コンピューター上で実行する複数の BizTalk Server グループを作成できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つのホスト コンピューターのホスト オペレーティング システム。  
  
- **展開と管理の容易さ**の統合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]より少ない物理サーバーにコンピューターが展開を簡略化します。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] .vhd ファイルを使用して、物理および仮想のコンピューターの展開の簡略化されたメソッドを使用します。 さらに、包括的な HYPER-V 管理ソリューションは、System Center Virtual Machine Manager で使用することができます。 System Center Virtual Machine Manager に関する詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)します。  
  
- **フォールト トレランスのサポートを通じて、HYPER-V がクラスタ リングの**のため、HYPER-V をクラスター対応のアプリケーション、Windows Server 2008 ネイティブ ホストのクラスタ リングを HYPER-V 仮想化環境で作成された仮想マシンのサポートを提供します。  
  
- **スケール アウト - の容易さ**の追加の処理能力、ネットワーク帯域幅、および記憶域の容量を確保できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションをゲストのホスト コンピューターから使用可能なリソースを追加して迅速かつ簡単に分配仮想マシン。 ホスト コンピューターがアップグレードされたこと、または機能を持つホスト コンピューターに、ゲスト仮想マシンを移動することが必要です。 ライブ マイグレーション機能[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]パフォーマンスやスケーリング、最適な統合の最良の物理コンピューターをユーザーに影響を与えることがなく Vm を実行中を移動することができます。  
  
- **ハードウェアのリソースの統合**複数の物理サーバーに簡単に統合できます比較的少数のサーバー、HYPER-V による仮想化を実装することで。 統合には、展開済みのハードウェア リソースの完全な使用が対応しています。  
  
  詳細についての詳細については、HYPER-V のメリット、機能を提供します、次を参照してください。 [Hyper-v による仮想化](http://go.microsoft.com/fwlink/?LinkID=202438)します。