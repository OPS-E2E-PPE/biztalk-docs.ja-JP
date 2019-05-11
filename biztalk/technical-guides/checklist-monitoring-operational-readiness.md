---
title: チェックリスト:運用準備状況の監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef77ccc2-1d39-4e78-8fea-5c17d05c8174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ece8f6b6aea58b37bf5e8f940f1f6fb197970ea4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399352"
---
# <a name="checklist-monitoring-operational-readiness"></a>チェックリスト:運用準備状況の監視
このトピックでは、運用環境を監視するときに従う必要のある手順[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。  


|                                                                                                                                                                      手順                                                                                                                                                                       |                                                                                                  リファレンス                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                           選択し、BizTalk アプリケーションとインフラストラクチャの監視戦略を実装します。                                                                                                                           |                                                [BizTalk Server 環境の監視](../technical-guides/monitoring-the-biztalk-server-environment.md)                                                 |
|                                                                                                                                                            ディスク使用量を監視します。                                                                                                                                                             |                                                              [ディスクの使用領域の監視](../technical-guides/monitoring-disk-space-usage.md)                                                               |
| モニターの SQL Server:<br /><br /> -確認ハウジングの SQL Server を実行しているコンピュータを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースが監視されています。<br />-ことを確認、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ジョブの監視されています。 |            -   [SQL Server の監視](../technical-guides/monitoring-sql-servers.md)<br />-   [BizTalk Server データベースの監視](../technical-guides/monitoring-biztalk-server-databases.md)            |
|          BizTalk アプリケーションを監視します。<br /><br /> -既存の規則またはカスタムの BizTalk アプリケーションを監視するカスタム管理パックにルールのコピーを変更します。<br />-定義された各ルールのアクションを作成します。<br />-手動のタスクを自動化する、反復的なプロセスを作成します。<br />-手動のタスクを自動化するのにしきい値規則を使用します。          | -   [アプリケーションとホスト インスタンスの監視](../technical-guides/monitoring-applications-and-host-instances.md)<br />-   [BizTalk Server2 の監視](../technical-guides/monitoring-biztalk-server2.md) |

## <a name="in-this-section"></a>このセクションの内容  

-   [ディスクの使用領域の監視](../technical-guides/monitoring-disk-space-usage.md)