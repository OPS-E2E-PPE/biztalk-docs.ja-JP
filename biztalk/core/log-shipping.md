---
title: ログ配布 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- log shipping
ms.assetid: 25bc9724-1c99-43d0-8cd1-3ed8eaa60268
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb0eb7d8c10d8e186f009cda82480490ef0df9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380554"
---
# <a name="log-shipping"></a>ログ配布
ログ配布は、ダウンタイムを短縮する、システム障害が発生した場合、ウォーム バックアップとも呼ばれるスタンバイ サーバーの機能を提供します。  
  
 分散データベース設計が[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]あります間で同期させる特定のバックアップを作成するときに、バックアップを復元できます をポイントします。 トランザクションが複数のデータベースにまたがることができます。場合、1 つのデータベースがオフラインになり、復元する必要がありますし、関連のすべてのデータベース復元しなければなりません 1 つのポイントでシステムが一貫性のある状態であることを確認します。 すべてのデータベースは、分散トランザクションに参加します。 詳細については、次を参照してください。[バックアップと、BizTalk Server データベースを復元](../core/backing-up-and-restoring-the-biztalk-server-databases.md)します。  
  
 Microsoft SQL Server のログ マーキングを使用してデータベースのバックアップ セットを生成する自動プロセスを提供する BizTalk Server のバックアップ ジョブ。 これらのバックアップ セットには、復元プロセス中に使用する同期ポイントが含まれます。 BizTalk Server のバックアップ ジョブによって生成されたデータベースのセットを復元するプロセスの一環として、各データベースの前回のログ バックアップ ファイルは、2 番目の最後の記号を使用して、特定のログ マークに復元されます。 これにより、データベースを一貫性のある状態に復元し、失われたデータの量を大幅に短縮することができます。 ログ マーク前に、最後の 1 つを使用する必要があります。 SQL Server には、ログ配布機能が含まれますが、のみをバックアップして、BizTalk Server データベースを復元するときの BizTalk Server ログ配布機能を使用する必要があります。  
  
> [!NOTE]
>  使用するため、SQL Server 単純復旧モデルがサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースを単純復旧モデル、トランザクション ログをバックアップできませんし、そのため、最新のバックアップ以降のアクティビティのレコードを保持はしないためです。  内のデータの整合性を確保する、完全復旧モデルを使用する SQL Server を構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース バックアップ セットです。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)