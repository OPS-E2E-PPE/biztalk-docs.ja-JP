---
title: BizTalk Server ログ配布が Windows クラスター名と IP アドレスを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2696f608f13244d5f00922b01d9e069a0ad6268d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401060"
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a>BizTalk Server ログ配布、Windows クラスター名と IP アドレスを使用します。
簡略化することは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのインスタンスを使用してログ配布、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター内の元と移行先サーバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布シナリオ。 次に、障害復旧イベントが発生した場合データベースの回復が簡略化だけで、名前と、クラスターに関連付けられている IP アドレス リソースを切り替えることで[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]以下に示すようにインスタンスします。 このアプローチを使用する場合は、トピックで説明したように、UpdateDatabase.vbs スクリプトを実行する必要はありません[Backup BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)のため、データベース名は変更されません。  
  
> [!NOTE]
>  クラスター化のフォールト トレランスを強化する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスをクラスター化された[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスを地理的に区切る必要があります。  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a>Windows Server クラスターの名前と IP を使用して配布を BizTalk Server のログを実装するには、アドレスのリソース  
  
1. 運用環境の BizTalk server を停止します。  
  
2. 実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セカンダリに配布の復元をログイン[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター。  
  
3. トピックで説明されている手順に従います[を構成する BizTalk Server のログ配布](../technical-guides/configuring-biztalk-server-log-shipping.md)を再構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布できるように、セカンダリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスがソース グループになり、プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスが移動先のグループではようになりました。  
  
4. Ip アドレスを停止し、ネットワーク名リソース PublicSQLClustername プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。  
  
5. 構成して、セカンダリで PublicSQLClustername IP とネットワーク名クラスター リソースを開始[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。  
  
6. 運用環境の BizTalk server を起動します。  
  
7. ログ配布の復元を確認します。  
  
8. 開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働サイト上のサービスに関連します。  
  
   次の手順を実行した後は、BizTalk グループがセカンダリを指している[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスの次の図に示すようにします。  
  
   次の図は、構成する方法を示しています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのクラスター化されたインスタンスを使用してログ配布[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]移動、クラスター化された名前と IP アドレス リソースとします。  
  
   ![クラスター名と IP を使用して BizTalk ログ配布](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")  
  
   **Windows Server クラスターの名前と IP アドレス リソースを使用して BizTalk Server のログ配布の実装**  
  
## <a name="see-also"></a>参照  
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)   
 [ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)   
 [バックアップ BizTalk Server ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)