---
title: "マスター シークレット サーバーの高可用性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b99cb04-61a5-41cc-a409-35897c17b789
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f366eb2827859f8d720c74e670808aebfb0665b2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="high-availability-for-the-master-secret-server"></a>マスター シークレット サーバーの高可用性
SSO は、ため、全体的な Microsoft BizTalk Server インフラストラクチャの重要な一部のマッピングの資格情報やシングル サインオン エンタープライズ シングル サインオン (SSO) 機能を使用しない場合でも[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SSO を使用してセキュリティで保護されたポートの情報構成します。 ポートの構成データを暗号化して、SSO データベースに格納します。 各 BizTalk サーバーでは、ポートの構成データを暗号化および暗号化に使用する SSO サービス (ENTSSO.exe) があります。  
  
 SSO サービスが起動時に、マスター シークレット サーバーから暗号化キーを取得します。 この暗号化キーには、マスター シークレットが呼び出されます。 マスター シークレット サーバーは、他の SSO サービスを維持し、マスター シークレットを配布する追加のサブサービスを持つです。 マスター シークレットが取得された後は、SSO サービスはキャッシュします。 60 秒ごとに、SSO サービスは、マスター シークレット サーバーとマスター シークレットを同期します。  
  
 マスター シークレット サーバーが失敗し、SSO サービスは、その更新間隔のいずれかで障害を検出、SSO サービスおよびすべてのランタイム操作に失敗しました。 を含む、サーバーの資格情報の復号化する前に実行されていた正常に続行します。 ただし、新しい資格情報またはポートの構成データを暗号化することはできません。 したがって、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境、マスタ シークレット サーバーの可用性に依存しています。  
  
## <a name="making-the-master-secret-server-available"></a>マスター シークレット サーバーの可用性を確保する方法  
 SSO システムの可用性のための[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、生成されるとすぐには、マスター シークレットをバックアップすることが重要です。 マスター シークレットを失うことは、SSO システムがそのマスター シークレットを使って暗号化したデータを失うことを意味します。 マスター シークレットのバックアップの詳細については、次を参照してください。[バックアップ マスター シークレットをする方法](http://go.microsoft.com/fwlink/?LinkID=151934)(http://go.microsoft.com/fwlink/?LinkID=151934)、BizTalk Server のヘルプ。  
  
 マスター シークレット サーバーの可用性は、次の 2 とおりの方法で確保することができます。  
  
-   **使用できないが、高可用性ではない**です。 マスター シークレット サーバーが、使用できなくなったとマスター シークレット サーバーと、このサーバーでマスター シークレットを復元するもう 1 つの SSO サーバーを昇格することができますし、手動で通知するように Microsoft System Center Operations Manager イベントを作成することができます。  
  
     この構成では、高可用性、ほとんどのシナリオだけで十分ができますをスケール アウト、受信、送信、および処理ホストと一致します。  
  
-   **高可用性**です。 マスター シークレット サーバーの冗長性を確保するには、Windows クラスタリングを使用して別にマスター シークレット サーバーをクラスター化するか、マスター シークレット サーバーを既存のデータベース クラスター上に構成します。 マスター シークレット サーバーによって提供されるサービスは、それほど多くのリソースを消費しません。データベース クラスターにインストールしたとしても、データベースの機能やパフォーマンスに影響を与えることはありません。 次の図は、マスター シークレット サーバーに高水準の可用性を確保する方法を示したものです。  
  
     ![高可用性のマスター シークレット サーバー](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
     この構成では高い可用性が実現される反面、追加のハードウェア リソースが必要になります。 SSO の高可用性インストール オプションの詳細については、次を参照してください。[高可用性 SSO インストール オプション](http://go.microsoft.com/fwlink/?LinkId=156838)(http://go.microsoft.com/fwlink/?LinkId=156838)、BizTalk Server のヘルプ。  
  
     このセクションには、上の高可用性クラスター リソースとして、SSO マスター シークレット サーバーを構成する方法の詳細情報が含まれています、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。  
  
    > [!NOTE]  
    >  高可用性ソリューションのハードウェア リソースを減らすためには、クラスター リソースとして、マスター シークレット サーバーを追加することができます、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]クラスター。 注意する必要はありませんを購入する追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SSO をインストールするライセンス サービス、SQL Server を実行しているコンピューターにします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [マスター シークレット サーバーのクラスタリング](../technical-guides/clustering-the-master-secret-server.md)  
  
-   [新しいマスター シークレット サーバーを手動で指定する](../technical-guides/designating-a-new-master-secret-server-manually.md)  
  
## <a name="see-also"></a>参照  
 [高 Availability2 の計画](../technical-guides/planning-for-high-availability2.md)   
 [BizTalk ホストの高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [データベースの高可用性](../technical-guides/high-availability-for-databases.md)