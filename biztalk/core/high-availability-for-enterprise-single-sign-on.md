---
title: エンタープライズ シングル サインオンの高可用性 |Microsoft Docs
ms.custom: ''
ms.date: 2016-02-29
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, availability
- high availability, SSO
- Master Secret server, high availability
- SSO, high availability
ms.assetid: 6c631b5c-7147-4cc0-b58a-6749e83df9d3
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fd572db5425b86a422fd1cca574ba7aba2e4262
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387593"
---
# <a name="high-availability-for-enterprise-single-sign-on"></a>エンタープライズ シングル サインオンの高可用性
資格情報のマッピングやシングル サインオンにエンタープライズ シングル サインオン (SSO) 機能を使用していない場合でも、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の全体的なインフラストラクチャの中で SSO はきわめて重要な役割を果たしています。これは BizTalk Server で、受信場所に対する情報のセキュリティを確保するために、SSO が使用されているためです。  
  
 SSO サービスをインストールする 1 台目のコンピューターは、マスター シークレット サーバーとして構成する必要があります。 マスター シークレット サーバーは、マスター シークレット (暗号化キー) を格納する SSO サーバーです。 マスター シークレットとは、SSO システムが、SSO データベースに格納したデータの暗号化および復号化に使用する暗号化キーのことです。  
  
 SSO サーバーに障害が発生しても、同じホスト インスタンスを実行する他の BizTalk Server コンピューター (SSO サーバー) が用意されていれば、その SSO サーバーが処理を引き継ぎます。 つまり、マスター シークレット サーバーの機能は失われることなく、BizTalk Server が処理を続行できます。  
  
 マスター シークレット サーバーで障害が発生した場合も、それ以前に実行されていた処理は、資格情報の復号化を含めてすべて正常に続行されます。 ただし、それ以降、新たに資格情報を暗号化することはできなくなります。 BizTalk Server 環境は、可用性の点でマスター シークレット サーバー対する依存関係があります。この概念を示したものが次の図です。  
  
 ![障害点](../core/media/tdi-highava-pointsfailure-mss.gif "TDI_HighAva_PointsFailure_MSS")  
  
> [!NOTE]
>  マスター シークレット サーバーが利用できなくなっても、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホスト インスタンスは以下の状態になるまで、メモリ内にキャッシュされたマスター シークレットのコピーを使用することでそのままランタイム操作を実行できます。  
> 
> - ホスト インスタンスが再起動する。  
>   -   BizTalk ホスト インスタンスを実行するコンピューター上の SSO サービスが再起動する。  
>   -   SSO マスター シークレットが変更される。  
> 
>   SSO サービスが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューター上で再起動した場合、または SSO マスター シークレットが変更された場合、キャッシュされたマスター シークレットのコピーがメモリから解放され、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はマスター シークレットの別のコピーを取得するため、マスター シークレット サーバーと通信できなければなりません。 マスター シークレット サーバーが利用できない場合、暗号化のためにマスター シークレット サーバーへのアクセスを必要とする管理操作は失敗します。  
  
## <a name="making-the-master-secret-server-available"></a>マスター シークレット サーバーの可用性を確保する方法  
 SSO システムの可用性、ひいては、BizTalk Server 環境の可用性を確保するためには、マスター シークレットが生成された時点で速やかにバックアップすることが不可欠です。 マスター シークレットを失うことは、SSO システムがそのマスター シークレットを使って暗号化したデータを失うことを意味します。 マスター シークレットのバックアップの詳細については、次を参照してください。[バックアップ マスター シークレットを方法](../core/how-to-back-up-the-master-secret.md)します。  
  
 マスター シークレット サーバーの可用性は、次の 2 とおりの方法で確保することができます。  
  
-   **使用できますが、高可用性ではありません。** マスター シークレットは、すべての SSO サーバーのメモリ内にキャッシュされるため、マスター シークレット サーバーに障害が発生してもランタイムの操作は続行します。 ただし、ポート構成または SSO 構成を変更することはできなくなります。 BizTalk Server ランタイムは問題なく処理を続行しますが、設計上の変更を加えることは一切できません。  
  
     決して高い水準の可用性を実現することはできませんが、ほとんどの場合、この構成でも一定水準の可用性を確保することはできます。また、受信ホスト、送信ホスト、および処理ホストをスケールアウトすることもできます。  
  
-   **高可用性。** マスター シークレット サーバーの冗長性を確保するには、Windows クラスタリングを使用して別にマスター シークレット サーバーをクラスター化するか、マスター シークレット サーバーを既存のデータベース クラスター上に構成します。 マスター シークレット サーバーによって提供されるサービスは、それほど多くのリソースを消費しません。データベース クラスターにインストールしたとしても、データベースの機能やパフォーマンスに影響を与えることはありません。 次の図は、マスター シークレット サーバーに高水準の可用性を確保する方法を示したものです。  
  
     ![高可用性のマスター シークレット サーバー](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
     この構成では高い可用性が実現される反面、追加のハードウェア リソースが必要になります。 SSO の高可用性インストール オプションの詳細については、次を参照してください。[高可用性 SSO インストール オプション](../core/high-availability-sso-installation-options.md)します。 このセクションでは、Windows Server クラスターにおける SSO マスター シークレット サーバーの高可用性クラスター リソースとしての構成について詳しく説明します。  
  
    > [!NOTE]
    >  高水準の可用性を実現するソリューションで、ハードウェア リソースをできるだけ抑えるためには、マスター シークレット サーバーを SQL Server クラスターのクラスター リソースとして追加します。 別のコンピューターで、SSO サービスをインストールする追加の BizTalk Server のライセンスを購入する必要はありません。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server データベースをクラスタ リング](../core/clustering-the-biztalk-server-databases1.md)   
 [高可用性 BizTalk Server 環境を作成します。](../core/creating-a-highly-available-biztalk-server-environment.md)   
 [マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)