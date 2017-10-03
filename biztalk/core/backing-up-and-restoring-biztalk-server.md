---
title: "バックアップと復元の BizTalk Server |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1adac25b23c69b51e07ed5f30768d046a453887a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-and-restoring-biztalk-server"></a>BizTalk Server のバックアップと復元
ハードウェアに障害が発生した場合に備えて、BizTalk Server のデータベースとコンポーネントの適切なバックアップを取っておくことは、必須の作業です。 適切なバックアップを用意しておけば、データの損失を最小限にとどめて障害から回復することができます。 BizTalk Server をどのように復元するかは、ハードウェア障害が発生したシステムにインストールされているコンポーネントによって異なります。 ここでは、次のようなハードウェア障害が発生した場合を想定します。  
  
 **BizTalk Server を実行しているコンピューターでのハードウェア障害**  
  
 BizTalk Server を実行しているコンピュータでハードウェア障害が発生した場合、BizTalk グループが高可用性を意図して設計されていないと、システムのダウンタイムやパフォーマンスの低下が発生する可能性があります。 高可用性の BizTalk グループを作成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)です。  
  
 ハードウェア障害が発生した後、BizTalk Server を別のコンピュータで実行できるようにするには、最初のコンピュータの BizTalk Server コンポーネントをバックアップしておく必要があります。 バックアップし、BizTalk Server を実行しているコンピューターを復元する方法の詳細については、次を参照してください。 [、コンピューターを実行している BizTalk Server のバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)と[BizTalk Server を実行しているコンピューターを回復する](../core/recovering-a-computer-running-biztalk-server.md)です。  
  
 **SQL Server を実行しているコンピューターでのハードウェア障害**  
  
 SQL Server クラスタリングを使用すると、SQL Server を実行しているコンピュータでハードウェア障害が発生した場合のリスクを最小限に抑えることができます。 ただし、SQL Server クラスタリングを使用していても、BizTalk Server データベースを格納している SQL Server で回復できないハードウェア障害が発生することもあります。 たとえば、データ層全体に障害が発生した場合などは、 最新のバックアップ データベースを復元して、BizTalk グループを回復します。  
  
 詳細については、BizTalk Server データベースのフォールト トレランスを提供する、次を参照してください。 [BizTalk Server データベースの高可用性の実現](../core/providing-high-availability-for-biztalk-server-databases.md)です。 ダウンタイムが発生した致命的な SQL Server の障害の場合の手順に従ってください[をバックアップおよび BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)です。  
  
 SQL Server と BizTalk Server の両方がインストールされているコンピュータでハードウェア障害が発生した場合は、BizTalk Server データベースを復元した後、BizTalk Server コンポーネントを復元してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チェックリスト: バックアップと復元](../core/checklist-backup-and-restore.md)  
  
-   [バックアップと復元のベスト プラクティス](../core/best-practices-for-backup-and-restore.md)  
  
-   [バックアップと、BizTalk Server データベースの復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [BizTalk Server を実行しているコンピューターの災害復旧](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md)