---
title: BizTalk Server Databases1 をクラスタ リング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, how to
- clustering, SQL Servers
- SQL Server, clustering
- BizTalk Server Configuration Wizard
- high availability, databases
- clustering, BizTalk Server Configuration Wizard
- clustering, databases
- clustering, prerequisites
ms.assetid: 9a1ed843-483b-4a56-961b-bc6801a07b64
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8a74f78098092f07b47e08b8f260d61129c739e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976675"
---
# <a name="clustering-the-biztalk-server-databases"></a>BizTalk Server データベースのクラスター化
このセクションでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ソリューションに高可用性を導入するためのガイドラインを示します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに障害が発生すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境は正常に機能することができなくなります。 次の図に示すように、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースに対して、Microsoft SQL Server クラスターを作成することによって高可用性を確保できます。  
  
 ![BizTalk Server のデータベース層](../core/media/tdi-highava-sqlcluster.gif "TDI_HighAva_SQLCluster")  
  
 高可用性を実現する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベース、SQL Server および使用するための共有ディスク アレイを実行している Windows Server フェールオーバー クラスターで少なくとも 2 台のコンピューターが必要です。  
  
## <a name="procedures-for-clustering-the-databases"></a>データベースをクラスター化するための手順  
  
#### <a name="before-you-start"></a>開始前の準備  
  
1. BizTalk Server 環境のドメイン グループを作成する場合は、Active Directory ドメイン グローバル グループを作成する必要があります。  
  
2. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールして構成する前に、SQL Server クラスターを構成します。 SQL Server のクラスタ リングの詳細については、次を参照してください。 [Always On フェールオーバー クラスター インスタンス](https://technet.microsoft.com/library/ms189134.aspx)します。  
  
3. さらに、マスター シークレット サーバーをクラスター化する場合は、マスター シークレット サーバーを最初に構成しておく必要があります。 エンタープライズ シングル サインオンの高可用性に関する詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)します。  
  
#### <a name="to-run-the-biztalk-server-configuration-wizard"></a>BizTalk Server の構成ウィザードを実行するには  
  
1. ランタイム サーバーに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールします。  
  
2. BizTalk 構成プログラムを起動します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。  
  
3. 手順に従って[のインポートとエクスポートの BizTalk Server 構成](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)カスタム構成を適用します。 BizTalk データベースの SQL Server クラスターを指定するには、SQL Server クラスターの名前を入力、**データベース**」の説明に従って、構成プログラムのダイアログ、**データベースの編集**セクションこのトピックでは。  
  
4. 次の手順で BizTalk Server の構成を完了[BizTalk Server の構成](../install-and-config-guides/configure-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [高可用性 BizTalk Server 環境を作成します。](../core/creating-a-highly-available-biztalk-server-environment.md)