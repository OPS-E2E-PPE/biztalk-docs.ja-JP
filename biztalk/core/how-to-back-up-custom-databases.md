---
title: カスタム データベースをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba90f39a90e2a80abda1a00214aafec48c6ea419
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387086"
---
# <a name="how-to-back-up-custom-databases"></a>カスタム データベースのバックアップ方法
カスタム データベースは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と一緒にインストールされないので、BizTalk Server のバックアップ ジョブによるバックアップ対象のデータベースの既定リストにも含まれていません。 BizTalk Server のバックアップ ジョブでカスタム データベースをバックアップする場合は、そのデータベースを BizTalk Server のバックアップ ジョブに手動で追加する必要があります。  
  
## <a name="prerequisites"></a>前提条件  
  
1. 完全復旧モデルを使用するように SQL Server を構成して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベース バックアップ セットのデータの整合性を確保する必要があります。  詳細については、次を参照してください。[ログ配布](../core/log-shipping.md)します。  
  
2. カスタム データベースをバックアップするには、バックアップ対象の各データベースにアクセスできるユーザー アカウントでログオンする必要があります。  
  
    BizTalk Server には、BTS_BACKUP_USERS という名前の SQL Server ロールが含まれているため、データベースのバックアップに使用するユーザー アカウントは、SQL Server 内でシステム管理者のアクセス許可を必要としません。ただし、バックアップ プロセスを制御するプライマリ サーバーは例外です。  
  
    使用しているユーザー アカウントでデータベースをバックアップするように設定する場合は、次の点に注意してください。  
  
   -   このユーザーの SQL Server ログオン アカウントを作成し、このユーザーを各サーバーの BizTalk BTS_BACKUP_USERS ロールに割り当てる必要があります。  
  
   -   BizTalk Server バックアップ ジョブは、SQL Server エージェント サービスに使用されるユーザー アカウントとは異なるユーザー アカウントで実行されるように構成できます。  
  
   -   SQL Server エージェント サービスは、ドメイン アカウントで実行する必要があります。 すべてのデータベースが同じコンピューターに存在する場合は、ローカル アカウントを使用するように SQL Server エージェントを構成してもかまいません。  
  
### <a name="to-back-up-custom-databases"></a>カスタム データベースをバックアップするには  
  
1. 新しいデータベースに各種のオブジェクトを構築します。  
  
   - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema ディレクトリを参照し、バックアップするすべてのカスタム データベースに対して Backup_Setup_All_Procs.sql と Backup_Setup_All_Tables.sql を実行します。 これにより、必要なプロシージャ、テーブル、およびロールが作成され、ストアド プロシージャに対するアクセス許可が割り当てられます。  
  
2. 次の構成を実行します。  
  
   -   BizTalk 管理データベースがホストされている SQL Server を、新しいデータベースがホストされる SQL Server にリンクします。 管理用 SQL Server で実行される SQL Server エージェント サービスには、すべての (つまり、バックアップ対象データベースが存在する) コンピューターにマップされたドメイン アカウントを使用する必要があります。 すべてのデータベースが同じコンピューターに存在する場合、この手順は省略できます。 この処理は自動的に行われます。  
  
   -   新しいデータベースをホストする SQL Server に対し、管理用 SQL Server の SQL Server エージェント サービスを実行するアカウント用のログインを追加します。 すべてのデータベースが同じコンピューターに存在する場合、この手順は省略できます。  
  
   -   新しいデータベースに、直前の手順で作成したログインのユーザーを追加し、さらに、このユーザーを BTS_BACKUP_USERS ロールに追加します。 このロールは手順 1. のスクリプトによって作成されたもので、その際に、必要なプロシージャの実行権限も与えられています。  
  
3. SQL Server Enterprise Manager または SQL Server Management Studio を使用して、BizTalk 管理 (BizTalkMgmtDb) データベースの変更、 **adm_OtherBackupDatabases**テーブルごとのカスタム データベースの行を含める。  
  
4. 次の表を参考にして、対応する列に新しいサーバー名とデータベース名を入力します。  
  
   |[列]|値|  
   |------------|-----------|  
   |DefaultDatabaseName|カスタム データベースのフレンドリ名。|  
   |DatabaseName|カスタム データベースの名前。|  
   |ServerName|SQL Server を実行するコンピューター名。|  
   |BTSServerName|BizTalk Server の名前。 実際にはこの値は使用されませんが、この列の値を空にすることはできません。|  
  
   これで、BizTalk Server のバックアップ ジョブを次に実行したときに、カスタム データベースがバックアップされるようになります。  
  
## <a name="see-also"></a>参照  
 [バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [バックアップおよび復元に関する詳細情報](../core/advanced-information-about-backup-and-restore1.md)