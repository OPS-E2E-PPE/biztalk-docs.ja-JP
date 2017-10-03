---
title: "Hyper V を BizTalk Server ソリューションを展開するメリットを潜在的な環境を仮想化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 588c70f0-68f0-4e58-8f3d-aa6834397bd4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9602a48b0deb4eeddc6f10b2d529d68d94cc781a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a>仮想化環境の Hyper V を BizTalk Server ソリューションを展開する潜在的なメリット
このトピックでは、展開する次の利点の一部について説明します、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HYPER-V 仮想環境にソリューションです。  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a>HYPER-V で、BizTalk Server ソリューションを実行する利点は、環境を仮想化  
 HYPER-V 仮想化環境で実行する BizTalk Server ソリューションを配置するには、次のような柔軟性と機能は提供します。  
  
-   **1 台の物理コンピューター - 複数の個別の論理セキュリティ境界を定義する機能**HYPER-V は個別の論理的なセキュリティの境界、または 1 つの物理ハードウェア リソース内のパーティションの作成に対応します。 パーティションは、オペレーティング システムが実行される、ハイパーバイザーによってサポートされる分離の 1 つの論理単位です。 たとえばをインストールするときに、これを行うにはことはできませんが、1 台の HYPER-V ホスト コンピューターで実行する複数の BizTalk Server グループを作成できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]単一のホスト コンピューターのホスト オペレーティング システムにします。  
  
-   **使いやすさの展開と管理 –**の統合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]より少ない物理サーバーにコンピューターの展開を簡略化します。 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].vhd ファイルを使用して、物理および仮想のコンピューターの展開の簡素化されたメソッドを使用します。 さらに、包括的な HYPER-V 管理ソリューションは、System Center Virtual Machine Manager と共に使用することができます。 System Center Virtual Machine Manager に関する詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303)です。  
  
-   **HYPER-V クラスターの許容範囲のサポートをフォールト**のための HYPER-V クラスターの対応するアプリケーションは、Windows Server 2008 は、ネイティブ ホストのクラスタ リングを HYPER-V 仮想化環境で作成されたバーチャル マシンのサポートを提供します。  
  
-   **スケール アウトの簡単な**の追加の処理能力、ネットワーク帯域幅、および記憶域の容量を確保できる、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションをゲストのホスト コンピューターから使用可能なリソースを追加で迅速かつ簡単に分配仮想マシン。 これには、ホスト コンピューターがアップグレードされたこと、またはより高機能なホスト コンピューターに、ゲスト仮想マシンを移動することがあります。 ライブ マイグレーション機能[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]実行されている Vm のパフォーマンス、スケーリング、または最適な統合が最適な物理コンピューターにユーザーに影響を与えずに移動することができます。  
  
-   **-ハードウェア リソースの統合**複数の物理サーバーに簡単に統合できます比較的少数のサーバーに HYPER-V で仮想化を実装することによってです。 統合は、配置済みのハードウェア リソースの使用を完全に対応します。  
  
 詳細を確認する詳細な機能と利点 HYPER-V については、次を参照してください。 [Hyper-v で仮想化](http://go.microsoft.com/fwlink/?LinkID=202438)です。