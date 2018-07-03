---
title: 'チュートリアル: Salesforce との BizTalk Server 2013 の統合 |Microsoft Docs'
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
ms.openlocfilehash: aecf9bcd1ef29a1324dc1b040388f17a19a71c52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011731"
---
# <a name="tutorial-integrating-biztalk-server-2013-with-salesforce"></a>チュートリアル: BizTalk Server 2013 を Salesforce と統合します。
校閲者: [Nick Hauenstein](http://social.msdn.microsoft.com/profile/nick.hauenstein/)、 [Steef-jan Wiggers](http://social.msdn.microsoft.com/profile/steef-jan%20wiggers)  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 新たなアダプターのハイブリッドなシナリオの多くを構成する、オンプレミスと Azure のテクノロジが可能になりましたに関連するについて説明します。 このチュートリアルでは、Salesforce を社内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に統合するように、一部の新しいアダプターと [!INCLUDE[winazure](../includes/winazure-md.md)] を使用して、純粋にクラウドのエンティティを統合する手順を説明します。 開始する前に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と Salesforce を統合することで達成しようとするビジネス上の目的を理解しましょう。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と Salesforce に以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を加えたハイブリッド ソリューションを作成することもできますが、Web サービス (SOAP) を利用して Salesforce を統合すると、ソリューションがより複雑になる場合があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と新しいアダプターを使用すると、ソリューションがより簡単になります。  
  
## <a name="business-scenario"></a>ビジネス シナリオ  
 Northwind は販売パイプラインを通じた顧客の追跡のためのソリューションに Salesforce オンライン CRM システムを利用しています。 Salesforce システムで販売機会が作成されるたびに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] などの社内システムに通知を受けることで、他のダウンストリーム システムがそのデータを取得して他の関連するプロセスを開始できるようにしたいと Northwind は考えています。 Northwind は [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で利用できる新しいアダプターを使用し、[!INCLUDE[winazure](../includes/winazure-md.md)] の一部のコンポーネントを含むこのソリューションの導入を計画しています。 このソリューションにおけるエンド ツー エンドのデータ フローは次のようになります。  
  
- 営業担当者が Salesforce システムで "営業案件" を作成します。  
  
- 営業案件の状態が “Closed Won” に設定されると、[!INCLUDE[winazure](../includes/winazure-md.md)] 上にホストされるリレー エンドポイントに通知が送信されます。  
  
- 新しい WCF-BasicHttpRelay アダプターを使用して、通知情報が社内の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] システムに渡されます。  
  
- 通知の一部として受け取った情報を使用し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は新しい WCF-WebHttp アダプターを使用して Salesforce 内の REST エンドポイントを起動し、営業案件に関する詳細情報を取得します。  
  
- 最後に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は Salesforce から受け取った情報を使用して、社内の SQL Server データベース テーブルに発注エントリを作成します。  
  
  このソリューションで説明する統合の意図を達成するには、これらの一連の手順を実行する必要があります。 これらの手順のそれぞれに、ソリューションの作成を続けていく中で見ることになる、広範なアクティビティが含まれています。  
  
  次の図では、エンド ツー エンドの統合ソリューションを説明しています。  
  
  ![BizTalk Server と Salesforce の統合シナリオ](../core/media/bts-sf-scenario.gif "BTS_SF_Scenario")  
  
## <a name="prerequisites"></a>前提条件  
 このソリューションをセットアップするコンピューターには次のソフトウェアをインストールする必要があります。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]  
  
- [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]  
  
- [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]  
  
  次のサービスのサブスクリプションが必要です。  
  
- [!INCLUDE[winazure](../includes/winazure-md.md)] サブスクリプション  
  
- Salesforce Developer Edition アカウント  
  
## <a name="more-resources"></a>その他のリソース  
 このチュートリアルでは、だけでなく参照することできますも統合の詳細については、次のリソース[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で導入された新しいアダプターを使用して、Salesforce で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
- バーチャル ラボ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で Salesforce との統合は[ http://go.microsoft.com/fwlink/?LinkId=290930](http://go.microsoft.com/fwlink/?LinkId=290930)します。  
  
- このチュートリアルに基づいてサンプルをダウンロードできる[ http://go.microsoft.com/fwlink/?LinkId=290932](http://go.microsoft.com/fwlink/?LinkId=290932)します。  
  
## <a name="next-steps"></a>次のステップ
  
-   [手順 1: Service Bus 名前空間を作成する](../core/step-1-create-a-service-bus-namespace.md)  
  
-   [手順 2: Salesforce システムのセットアップ](../core/step-2-set-up-the-salesforce-system.md)  
  
-   [手順 3: Visual Studio での BizTalk Server ソリューションの作成](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)  
  
-   [手順 4: BizTalk Server ソリューションの構成](../core/step-4-configure-the-biztalk-server-solution.md)  
  
-   [手順 5: ソリューションのテスト](../core/step-5-test-the-solution.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server チュートリアル](../core/biztalk-server-tutorials.md)