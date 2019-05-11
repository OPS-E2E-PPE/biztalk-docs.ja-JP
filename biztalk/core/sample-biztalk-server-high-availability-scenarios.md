---
title: BizTalk Server の高可用性のシナリオのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- examples, high availability
- architecture, examples
- high availability, examples
- examples, architecture
- databases, clustering
- architecture, medium distributions
- scaling
- architecture, large distributions
ms.assetid: ad9e3f57-1a23-41c2-82c9-dc8e1b29ed4d
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 950f82a57c1f0be599fa9fbcceb4b6a590a0576e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393921"
---
# <a name="sample-biztalk-server-high-availability-scenarios"></a>サンプル BizTalk Server の高可用性のシナリオ
このトピックでは、Microsoft のシナリオを説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をホストのスケール アウト層から高可用性を提供します。 別々 のホスト機能と階層内の領域を分離することで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者は、各ホストの冗長性を確保し、他のホストとは独立してスケールします。 各機能領域の高可用性を実現するには、プライマリ関数ごとに個別のホストを作成する-受信、処理、送信、および追跡-クラスターと、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]データベースと、エンタープライズ シングル サインオン マスター シークレット サーバーです。  
  
## <a name="small-biztalk-server-deployments"></a>小規模の BizTalk Server の展開  
 最小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]両方 SQL Server の高可用性を提供する展開と[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]for SQL Server をアクティブ/アクティブ クラスター構成を持つ 2 台のコンピューターの構成されます。 両方のコンピューターには、環境内のすべての BizTalk ホストのインスタンスが含まれます。 1 台のコンピューターでは、障害が発生したり、エラーが発生した、他のコンピューターは、SQL Server と BizTalk Server の両方のサービスの可用性を維持します。 この構成できないため、マスター シークレット サーバーをクラスター対応していないため、高可用性は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト インスタンスが起動しない、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パッシブ クラスター化されたエンタープライズ シングル サインオン リソースのコンピューター。 マスター シークレット サーバーをクラスタ リングの詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)します。  
  
 小規模[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]5 未満のコンピューターを含む展開では、お勧め、BizTalk Server コンピューターから別のコンピューターで BizTalk Server データベースを含む SQL Server クラスターを実行します。 BizTalk Server コンピューターは、すべての BizTalk ホストを実行できます (受信、処理、および送信) します。 この展開を高可用性にするには、クラスターの SQL Server と、エンタープライズ シングル サインオン マスター シークレット サーバーと、環境内の各ホスト インスタンスを実行する 2 つの BizTalk サーバーがあります。  
  
 次の図は、高可用性である小規模の BizTalk Server 展開を示します。  
  
 ![小規模の BizTalk Server 展開](../core/media/tdi-highava-smalldepl.gif "TDI_HighAva_SmallDepl")  
  
## <a name="medium-sized-biztalk-server-deployments"></a>BizTalk Server の規模の展開  
 5 ~ 10 台のコンピューターを含む中規模の展開、BizTalk Server データベースを含む SQL Server と、エンタープライズ シングル サインオン マスター シークレット サーバーをクラスター化することをお勧めします。 自分のシナリオが受信集中型の場合は、専用の 2 つの BizTalk Server の高可用性ソリューションを提供する受信側のホスト インスタンスを実行したい場合があります。 2 つのコンピューターに、両方の処理を実行しているし、送信ホスト インスタンスをすることができます。 このようにするには、高可用性の展開が、両方の処理のホスト インスタンスを作成し、2 つの BizTalk サーバーでホストを送信します。 同様に、処理負荷の高いシナリオがあれば、処理ホストのインスタンスを実行し、受信側の両方のインスタンスを実行している残りの 2 つの BizTalk サーバーし、送信ホストに 2 つの BizTalk サーバー専用にする可能性があります。  
  
 次の図は、受信側の操作に専用の 2 つの BizTalk Server で高可用性規模の BizTalk Server 展開を示しています。  
  
 ![Medium&#45;BizTalk Server の展開の規模](../core/media/tdi-highava-meddepl.gif "TDI_HighAva_MedDepl")  
  
 エンタープライズ シングル サインオンの高可用性に関する詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)します。  
  
## <a name="large-scale-biztalk-server-deployments"></a>BizTalk Server の大規模な展開  
 10 個以上のコンピューターを含む大規模な展開では、専用の受信、処理、および送信の各機能の個別の BizTalk Server コンピューターを割り当てます。 また、多くの BizTalk Server コンピューター グループである場合は場合、は、パフォーマンスを向上させるその他のメッセージ ボックス データベース コンピューターを含めることができます。 この場合、クラスター、メッセージ ボックス データベース、高可用性を提供する場合は、マスター シークレット サーバーをクリックします。  
  
 このような分散構成の柔軟性を示して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を評価および、配置内のエラーの特定のポイントを特定し、戦略的に、システムでこれらのポイントを削減するリソースを割り当てることができるためです。 今日のダイナミックなビジネス環境は、ワークロードの変動やビジネス要件も日々 変化するために、このような柔軟性を要求します。  
  
 アップグレードまたは新しいハードウェアを取得するのに追加のコストをかけるには、リソースの消費をあるコンピューターにいくつかのリソースを消費するコンピューターからリソースを移動することによって高可用性を実現するために既存のリソースを使用できます。  
  
 次の図は、大規模な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。  
  
 ![大規模な&#45;BizTalk Server の展開をスケール](../core/media/tdi-highava-largedepl.gif "TDI_HighAva_LargeDepl")  
  
 エンタープライズ シングル サインオンの高可用性に関する詳細については、次を参照してください。[エンタープライズ シングル サインオンの高可用性](../core/high-availability-for-enterprise-single-sign-on.md)します。  
  
## <a name="providing-high-availability-using-hyper-v-and-failover-clustering"></a>HYPER-V とフェールオーバー クラスタ リングを使用して高可用性の実現  
 Windows® Server 2008 HYPER-V の役割と Windows Server 2008 フェールオーバー クラスタ リング機能は、仮想化サーバー コンピューティング環境の高可用性を提供する同時使用できます。 BizTalk Server コンピューターとで使用される SQL Server コンピュータ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開を HYPER-V 仮想化環境にインストールされているし、フェールオーバー クラスタ リングによって高可用性になります。 HYPER-V でゲスト オペレーティング システムを実行に関連付けられているシステム リソースのコストがあるため、このようなソリューションを運用環境に展開する前に徹底的なパフォーマンス テストを実行することをお勧めします。 HYPER-V とフェールオーバー クラスタ リングを使用しての詳細についてはまとめて高可用性の仮想マシンを参照してください"HYPER-V ステップ バイ ステップ ガイド。HYPER-V とフェールオーバー クラスタ リング"で[ http://go.microsoft.com/fwlink/?LinkID=129113](http://go.microsoft.com/fwlink/?LinkID=129113)します。 展開の詳細については、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、HYPER-V の仮想化環境でダウンロードできる BizTalk Server の HYPER-V ガイドを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=189706](http://go.microsoft.com/fwlink/?LinkId=189706)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk ホストの高可用性を実現します。](../core/providing-high-availability-for-biztalk-hosts.md)   
 [BizTalk Server データベースの高可用性を実現します。](../core/providing-high-availability-for-biztalk-server-databases.md)   
 [Enterprise Single Sign-On の高可用性](../core/high-availability-for-enterprise-single-sign-on.md)