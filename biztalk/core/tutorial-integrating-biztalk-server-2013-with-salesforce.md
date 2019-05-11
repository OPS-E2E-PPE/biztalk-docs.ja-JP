---
title: チュートリアル:BizTalk Server 2013 を Salesforce と統合する |Microsoft Docs
description: Service Bus および BIzTalk Server を使用する Salesforce と統合するには
ms.custom: ''
ms.date: 12/07/2015
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c9ae51-3f48-4086-883b-ab4d5b6e62e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2757c2a36c86bb302859f0174e8c53b5bb397025
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399169"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a>チュートリアル:BizTalk Server 2013 を Salesforce と統合します。
校閲者:[Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)、 [Steef-jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 新たなアダプターのハイブリッドなシナリオの多くを構成する、オンプレミスと Azure のテクノロジが可能になりましたに関連するについて説明します。 ここでは、このチュートリアルでは、純粋なクラウド エンティティをオンプレミスと Salesforce の統合などを統合する方法を参照してください[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]いくつかの新しいアダプターを使用して、[!INCLUDE[winazure](../includes/winazure-md.md)]します。 を始める前に統合することで実現するビジネス目標を理解しましょう[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Salesforce とします。  
  
 でしたも作成ハイブリッド ソリューションに関する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と Salesforce の以前のバージョンに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューションは Web サービス (SOAP) を使用する Salesforce との対話に関連するはるかに複雑になりますが、します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、新しいアダプターをソリューションがより容易にします。  
  
## <a name="business-scenario"></a>ビジネス シナリオ  
 Northwind は、販売パイプラインを使用して顧客を追跡するためのソリューションとしての Salesforce オンライン CRM システムを使用します。 Northwind がなどのオンプレミス システムを希望するたびに、Salesforce で営業案件が作成される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通知を受ける他のダウン ストリーム システムがそのデータを選択し、関連するその他のプロセスを開始できるようにします。 使用可能な新しいアダプターを使用して、このソリューションを実装する計画を Northwind[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の一部のコンポーネントを含めることでも[!INCLUDE[winazure](../includes/winazure-md.md)]します。 これは、ようなソリューションが、エンド ツー エンドのデータ フローの検索です。  
  
- 営業担当者は、Salesforce システムで、"opportunity"を作成します。  
  
- ホストされているリレー エンドポイントに通知が送信された営業案件の状態が"Closed Won"に設定されている場合[!INCLUDE[winazure](../includes/winazure-md.md)]します。  
  
- 新しい Wcf-basichttprelay アダプターを使用して、通知情報が上に渡される[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オンプレミスがシステムに格納されています。  
  
- 通知の一部として受け取った情報を使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は営業案件に関する詳細を取得する、新しい Wcf-webhttp アダプターを使用して、Salesforce で REST エンドポイントを呼び出します。  
  
- 最後に、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Salesforce から受信した情報を使用して、社内の SQL Server データベース テーブルで、発注エントリを作成します。  
  
  これらは、このソリューションで説明されている統合目標を達成するために必要な手順のセットです。 これらの各手順には、見てソリューションの作成に進むとアクティビティの広範なセットが含まれます。  
  
  エンド ツー エンドの統合ソリューションを説明する図を次に示します。  
  
  ![BizTalk Server と Salesforce の統合シナリオ](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")  
  
## <a name="prerequisites"></a>前提条件  
 このソリューションを設定するコンピューターにインストールされている、次のソフトウェアが必要です。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
- [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
- [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
  次のサービスのサブスクリプションが必要です。  
  
- A[!INCLUDE[winazure](../includes/winazure-md.md)]サブスクリプション  
  
- Salesforce の Developer Edition アカウント  
  
## <a name="more-resources"></a>その他のリソース  
 このチュートリアルでは、だけでなく参照することできますも統合の詳細については、次のリソース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で導入された新しいアダプターを使用して、Salesforce で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- バーチャル ラボ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で Salesforce との統合は[ http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930)します。  
  
- このチュートリアルに基づいてサンプルをダウンロードできる[ http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932)します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [ステップ 1: Service Bus の Namespace を作成します。](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [手順 2:Salesforce システムを設定します。](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [手順 4:BizTalk Server ソリューションを構成します。](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [手順 5:ソリューションをテストします。](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)