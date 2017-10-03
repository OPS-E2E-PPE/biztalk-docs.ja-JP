---
title: "BizTalk Server のログ配布は Windows クラスター名と IP アドレスを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82ef6908-6009-4d06-8315-0bc85a0aad18
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8619ea6c4eea3eefee5b86282a29e0165d0fb074
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-log-shipping-using-a-windows-cluster-name-and-ip-address"></a>BizTalk Server のログ配布の Windows クラスター名と IP アドレスを使用して
簡略化することは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのインスタンスを使用してログ配布、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター内の元と移行先サーバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布のシナリオです。 次に、障害復旧イベントが発生した場合データベースの回復が簡略化だけで、名前と、クラスター化されたに関連付けられている IP アドレス リソースを切り替えることによって[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]以下に示すようをインスタンス化します。 このアプローチを使用する場合は、」の説明に従って、UpdateDatabase.vbs スクリプト実行する必要はありません[BizTalk Server のバックアップ ジョブでデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)のため、データベース名は変更されません。  
  
> [!NOTE]  
>  クラスター化されたのフォールト トレランスを向上させる[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンス、クラスター化された[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスを地理的に区切る必要があります。  
  
### <a name="to-implement-biztalk-server-log-shipping-using-a-windows-server-cluster-name-and-ip-address-resource"></a>Windows Server クラスターの名前と IP を使用して配布を BizTalk Server のログを実装するには、アドレスのリソース  
  
1.  実稼働の BizTalk サーバーを停止します。  
  
2.  実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セカンダリに配布の復元をログ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター。  
  
3.  トピックで説明した手順を[を構成する BizTalk Server ログ配布](../technical-guides/configuring-biztalk-server-log-shipping.md)を再構成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布できるようにセカンダリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスは、ソース グループになり、プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスが、対象のグループです。  
  
4.  Ip アドレスを停止し、ネットワーク名リソース PublicSQLClustername プライマリ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。  
  
5.  構成およびセカンダリ PublicSQLClustername IP とネットワーク名クラスター リソースを起動[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンス。  
  
6.  運用環境の BizTalk server を起動します。  
  
7.  ログ配布の復元を確認します。  
  
8.  開始[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働サイト上のサービスに関連します。  
  
 次の手順を実行すると、BizTalk グループが、セカンダリを指して[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター インスタンスに次の図に示すようにします。  
  
 次の図は、構成する方法を示しています。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の 2 つのクラスター化されたインスタンスを使用してログ配布[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]移動、クラスター化された名前と IP アドレス リソースとします。  
  
 ![クラスター名と IP を使用して BizTalk ログ配布](../technical-guides/media/5055689e-c26b-4077-a531-74a50fec1393.gif "5055689e-c26b-4077-a531-74a50fec1393")  
  
 **Windows Server クラスター名と IP アドレス リソースを使用した BizTalk Server のログ配布の実装**  
  
## <a name="see-also"></a>参照  
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)   
 [ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)   
 [バックアップの BizTalk Server のジョブ内のデータベースを復元する方法](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)