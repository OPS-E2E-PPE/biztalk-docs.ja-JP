---
title: マスター シークレット サーバーの高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b99cb04-61a5-41cc-a409-35897c17b789
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9227715e30405217cdb9c13c2dc83dc0e236eef8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975851"
---
# <a name="high-availability-for-the-master-secret-server"></a>マスター シークレット サーバーの高可用性
は SSO 資格情報と、シングル サインオンをマッピングするため、エンタープライズ シングル サインオン (SSO) 機能を使用しない場合でも、Microsoft BizTalk Server インフラストラクチャ全体の重要な部分、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でポートの情報をセキュリティで保護する構成します。 ポートの構成データが暗号化され、SSO データベースに格納されています。 各 BizTalk サーバーでは、ポートの構成データを暗号化および暗号化に使用する SSO サービス (ENTSSO.exe) があります。  
  
 SSO サービスを起動すると、マスター シークレット サーバーから暗号化キーを取得します。 この暗号化キーには、マスター シークレットが呼び出されます。 マスター シークレット サーバーには、別の SSO サービスを維持し、マスター シークレットを配布するその他のサブサービスですが。 マスター シークレットが取得された後は、SSO サービスはキャッシュします。 60 秒ごとに、SSO サービスは、マスター シークレット サーバーとマスター シークレットを同期します。  
  
 かどうかは、マスター シークレット サーバーは失敗し、SSO サービスは、その更新間隔のいずれかで障害を検出、SSO サービスと、資格情報の復号化を含むサーバーが、前に実行されていたすべてのランタイム操作正常に続行します。 ただし、新しい資格情報またはポートの構成データを暗号化することはできません。 そのため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境は、マスター シークレット サーバーの可用性に依存しています。  
  
## <a name="making-the-master-secret-server-available"></a>マスター シークレット サーバーの可用性を確保する方法  
 SSO システムの可用性のための[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、生成されるとすぐには、マスター シークレットをバックアップすることが重要です。 マスター シークレットを失うことは、SSO システムがそのマスター シークレットを使って暗号化したデータを失うことを意味します。 マスター シークレットのバックアップの詳細については、次を参照してください。[バックアップ マスター シークレットを方法](http://go.microsoft.com/fwlink/?LinkID=151934)(<http://go.microsoft.com/fwlink/?LinkID=151934>) BizTalk Server のヘルプ。  
  
 マスター シークレット サーバーの可用性は、次の 2 とおりの方法で確保することができます。  
  
- **使用できますが、高可用性ではない**します。 マスター シークレット サーバーが使用できなくなったとマスター シークレット サーバーと、このサーバー上にマスター シークレットを復元するもう 1 つの SSO サーバーを昇格することができますし、手動で、通知するように Microsoft System Center Operations Manager イベントを作成することができます。  
  
   この構成は高可用性ではありませんが、ほとんどのシナリオにとってあることができ、スケール アウト処理、送信、受信側のホストと一致します。  
  
- **高可用性**します。 マスター シークレット サーバーの冗長性を確保するには、Windows クラスタリングを使用して別にマスター シークレット サーバーをクラスター化するか、マスター シークレット サーバーを既存のデータベース クラスター上に構成します。 マスター シークレット サーバーによって提供されるサービスは、それほど多くのリソースを消費しません。データベース クラスターにインストールしたとしても、データベースの機能やパフォーマンスに影響を与えることはありません。 次の図は、マスター シークレット サーバーに高水準の可用性を確保する方法を示したものです。  
  
   ![高可用性のマスター シークレット サーバー](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
   この構成では高い可用性が実現される反面、追加のハードウェア リソースが必要になります。 SSO の高可用性インストール オプションの詳細については、次を参照してください。[高可用性 SSO インストール オプション](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838) BizTalk Server のヘルプ。  
  
   このセクションにはで、高可用性クラスター リソースとして、SSO マスター シークレット サーバーを構成する方法の詳細情報が含まれています、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。  
  
  > [!NOTE]
  >  高可用性ソリューションのハードウェア リソースを減らすためには、マスター シークレット サーバーを追加でクラスター リソースとして、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター。 注意する必要はありませんを購入する追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SSO をインストールするためのライセンス サービス、SQL Server を実行しているコンピューターにします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [マスター シークレット サーバーのクラスタリング](../technical-guides/clustering-the-master-secret-server.md)  
  
-   [新しいマスター シークレット サーバーを手動で指定する](../technical-guides/designating-a-new-master-secret-server-manually.md)  
  
## <a name="see-also"></a>参照  
 [高 Availability2 の計画](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)