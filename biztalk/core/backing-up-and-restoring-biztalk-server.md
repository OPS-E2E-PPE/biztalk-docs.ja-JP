---
title: バックアップと復元の BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe03a75a-1ea6-4ccc-9543-7989ec6b1cff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b04e6db4a125b2c90e3417c53d77b10e06f63ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358680"
---
# <a name="backing-up-and-restoring-biztalk-server"></a>BizTalk Server のバックアップと復元
ハードウェアの障害が発生した場合、BizTalk Server データベースとコンポーネントの適切なバックアップを取る必要があります。 ほとんどまたはまったくデータの損失を回復する適切なバックアップが有効になりません。 BizTalk Server を復元する方法は、ハードウェア障害が発生したシステムにインストールするコンポーネントに依存します。 このガイドでは、次のハードウェア障害のシナリオについて説明します。  
  
 **BizTalk Server を実行しているコンピューターでのハードウェア障害**  
  
 BizTalk Server を実行しているコンピューターでハードウェア障害は、システムのダウンタイムが発生する可能性があります。 または高可用性のため、BizTalk グループが設計されていない場合は、パフォーマンスを低下します。 高可用性の BizTalk グループを作成する方法の詳細については、次を参照してください。[高可用性の計画](../core/planning-for-high-availability3.md)します。  
  
 ハードウェア障害の後に BizTalk Server を実行するコンピューターを置換できることを確認するには、そのコンピューターで、BizTalk Server コンポーネントをバックアップする必要があります。 バックアップを作成して、BizTalk Server を実行しているコンピューターを復元する方法の詳細については、次を参照してください。 [、コンピューターを実行している BizTalk Server のバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)と[BizTalk Server を実行しているコンピューターを回復する](../core/recovering-a-computer-running-biztalk-server.md)します。  
  
 **SQL Server を実行しているコンピューターでのハードウェア障害**  
  
 SQL Server クラスタ リングを使用して SQL Server を実行するコンピューターのハードウェア障害のリスクを最小限に抑えることができます。 SQL Server クラスタ リングを使用する場合にもただし、ある可能性がありますの場合、BizTalk Server データベースを格納している SQL server を復旧不可能なハードウェア障害が発生したときにします。 たとえば、全体のデータ層は、障害を検出しました。 このような場合は、最新のバックアップされたデータベースのセットを復元することで、BizTalk グループを回復する必要があります。  
  
 フォールト トレランスを提供する BizTalk Server データベースの詳細については、次を参照してください。 [BizTalk Server データベースの高可用性の実現](../core/providing-high-availability-for-biztalk-server-databases.md)します。 場合は、ダウンタイムが発生した SQL Server の致命的なエラーには」の手順に従う必要があります[バックアップと、BizTalk Server データベースを復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)します。  
  
 SQL Server と BizTalk Server の両方がインストールされているコンピューターでハードウェア障害が発生した場合、BizTalk Server データベースを復元し、BizTalk Server コンポーネントを回復しください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チェックリスト:バックアップと復元](../core/checklist-backup-and-restore.md)  
  
-   [バックアップおよび復元のベスト プラクティス](../core/best-practices-for-backup-and-restore.md)  
  
-   [BizTalk Server データベースのバックアップと復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)  
  
-   [BizTalk Server を実行しているコンピューターのディザスター リカバリー](../core/disaster-recovery-for-computers-running-biztalk-server.md)  
  
-   [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)  
  
-   [BizTalk Server を実行しているコンピューターの復旧](../core/recovering-a-computer-running-biztalk-server.md)