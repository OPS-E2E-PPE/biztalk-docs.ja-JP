---
title: 指向ソリューションのサービスをインストールする前に |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, deployment prerequisites
ms.assetid: 865bd21c-e49a-4647-af91-fefee07ee806
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23f326a6fe028c5b7ea5edf60216c1933eccbdb6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="before-installing-the-service-oriented-solution"></a>サービス指向ソリューションをインストールする前に
単一のコンピューターにサービス指向ソリューションのスタブ バージョンをインストールするために必要な次のコンポーネントを用意する必要があります。  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]」をご覧ください。  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] でサポートされているソフトウェア  
  
-   IBM WebSphere MQ Client for Windows の最新バージョン  
  
    > [!NOTE]
    >  MQSeries Server は、このソリューションのスタブ バージョンで必要ありません。  
  
    > [!NOTE]
    >  IBM Web サイトから IBM WebSphere MQ Client for Windows をダウンロードできます。  
  
 単一のコンピューターにサービス指向ソリューションのインライン バージョンおよびアダプター バージョンをインストールするには  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)]」をご覧ください。  
  
    > [!NOTE]
    >  ドメイン アカウントは、エンタープライズ シングル サインオン (SSO) の資格情報をマップするために必要です。 BizTalk サービス用のドメイン アカウントおよび ENTSSO サービス アカウント用のドメイン アカウントを使用することをお勧めします。  
  
-   [!INCLUDE[bts2010R2](../includes/bts2010r2-md.md)] でサポートされているソフトウェア  
  
-   ローカル コンピューター上の MQSeries Server または MQSeries Server を実行しているコンピューターへのアクセス。 インライン バージョンを使用する場合、このソリューションのオーケストレーションを実行している BizTalk Server 上に MQSeries クライアント API を用意する必要があります。  
  
    > [!NOTE]
    >  MQSeries Server のバージョンは、BizTalk Server MQSeries アダプタで必要なバージョンに一致する必要があります。 これにより、フィックス パック (CSD10) が適用されている IBM WebSphere MQ for Windows のバージョン 5.3 以降を使用できます。  
  
    > [!NOTE]
    >  分散コンポーネント オブジェクト モデル (DCOM) によるサーバーの呼び出しを可能にする MQSeries などの機能を使用する際は、ネットワーク アドレス変換 (NAT) ベースのファイアウォールが無効になっていることを確認します。 クライアントは、実際の IP アドレスを使用してサーバーにアクセスできる必要があり、NAT ベースのファイアウォールによって、このアドレスはクライアントが認識できないように変換されます。  
  
-   メインフレームに必要なソリューションのバリエーションを使用している場合の CICS および Transaction X 対応の IBM メインフレーム。 この場合、CICS アプリケーション (COBOL コード) をメインフレームにインストールする必要があります。また、メインフレームにアクセスするには、Microsoft Host Integration Server (HIS) が必要です。  
  
     このソリューションに対応するメインフレームがない場合、ポートのバインドを変更して、Pending Transactions のスタブ Web サービスを使用できます。 メインフレームのトランザクションをエミュレートするため、Web サービスは、ローカルにトランザクションを生成します。 スタブ Pending Transactions Web サービスのポートのバインドを変更する方法の詳細については、次を参照してください。[インライン バージョンおよびサービス指向ソリューションのアダプター バージョンをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)です。  
  
-   Host Integration Server は、メインフレームに接続するために必要です。  
  
    > [!NOTE]
    >  Host Integration Server は、BizTalk Server の一部として含まれています。  
  
-   HTTPS 接続に使用する証明書を構成した Web サーバー。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [指向ソリューションのサービスを実行する方法](../core/how-to-run-the-service-oriented-solution.md)   
 [サービス指向ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-service-oriented-solution.md)