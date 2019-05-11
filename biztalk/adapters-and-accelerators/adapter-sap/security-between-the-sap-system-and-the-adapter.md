---
title: SAP システムとアダプター間のセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca967a375e1d64a7e3f720648fb7eb8ceede98b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372891"
---
# <a name="security-between-the-sap-system-and-the-adapter"></a>SAP システムとアダプター間のセキュリティ
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP セキュリティで保護されたネットワーク通信 (SNC) またはユーザー名パスワードの資格情報を SAP サーバーとの間の通信のセキュリティをサポートしています。 ユーザー名パスワード資格情報は、SAP システムに接続の認証のみを提供します。接続経由で交換されるデータのセキュリティは提供されません。 SNC とユーザー名のパスワード資格情報を同時に使用することはできません。  
  
## <a name="sap-secure-network-communications"></a>SAP のセキュリティで保護されたネットワーク通信  
 セキュリティで保護されたネットワーク通信 (SNC) は、SAP クライアントと SAP アプリケーション サーバー間で交換されるデータをアプリケーション レベルのセキュリティを提供する SAP システムのアーキテクチャでのソフトウェア レイヤーです。  
  
 SNC には次の利点があります。  
  
- SNC は、アプリケーション レベルのエンド ツー エンドのセキュリティを対象とします。 SNC は、(たとえば、SAPgui とシステムの SAP アプリケーション サーバー) 間の SNC で保護されている 2 つのコンポーネント間のすべての通信をセキュリティ保護に役立ちます。  
  
- SAP システムが、直接 (、やなどのシングル サインオン認証にスマート カードを使用) は提供しない追加のセキュリティ機能を実装することができます。  
  
- SNC 実装をカスタマイズすることができます。 任意のセキュリティ製品を使用し、使用するアルゴリズムを選択できます。  
  
- セキュリティ製品は、SAP システムのビジネス アプリケーションに影響を与えずに、いつでも変更できます。  
  
  SNC を使用する SAP サーバーとを実行しているクライアントの両方を構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
- セキュリティで保護されたネットワーク通信 (SNC) は、SAP サーバーに構成します。 ガイダンスについては、SAP のマニュアルを参照してください。  
  
- SAP クライアント Dll を持つコンピューター上と[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、インストールされている必要がある、SNC 関連の Dll。 これらの Dll の詳細については、次を参照してください。、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] [ソフトウェアの前提条件](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)します。  
  
- SNC を使用するアダプターを構成するには、SAP 接続 URI で UseSnc パラメーターを設定する必要があります。 SAP 接続 URI の詳細については、次を参照してください。 [SAP アダプターの接続 URI の構成](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)します。 また、設定する必要があります、 **SncLibrary**と**SncPartnerName**プロパティをバインドします。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
## <a name="user-name-password-credentials"></a>ユーザー名パスワード資格情報  
 接続 URI のアダプターにユーザー名パスワード資格情報を指定することができます。 アダプターは、接続を開くときに、SAP システムでユーザーの認証にこれらの資格情報を使用します。 これらの資格情報は、SAP システムへの接続承認のレベルを提供します。ただし、メッセージ レベルまたはトランスポート レベル認証 (承認) データをネットワーク上の移動は提供されません。  
  
 このため、適切なレベルの承認、認証、データ プライバシー、およびアダプターと SAP システムの間のデータ交換用のデータの整合性を確保しやすく、セキュリティ メカニズムを提供する必要があります。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、SAP システムの資格情報は、接続 URI で許可されているかどうかを決定します。 既定では、 **AcceptCredentialsInUri**が false と[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]資格情報が URI に含まれている場合に例外をスローします。 詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
 1 つの可能なメカニズムをネットワーク経由で複数のセキュリティを提供することは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープンな標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。  
  
 ユーザー名とパスワードは、接続 URI にクリア テキストとして指定されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]数により、これらの資格情報を指定することがより安全にメソッドを提供します。  
  
-   安全に BizTalk ソリューションでの SAP システムの資格情報を提供する方法については、次を参照してください。 [SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)します。  
  
-   安全にソリューションをプログラミングでの SAP システムの資格情報を提供する方法については、次を参照してください。 [SAP アダプターを使用したプログラミングをセキュリティで保護された](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)します。  
  
## <a name="security-concerns-for-inbound-scenarios"></a>受信シナリオのセキュリティ関連事項  
 SAP プログラム ID にアクセスできるすべてのリスナーはすべて SAP アイテム (Rfc、Idoc、および Trfc) プログラム ID に送信を受け取る可能性のあることができます。 プログラム ID には、複数のリスナーを登録すると、SAP は、リスナーのいずれかにそのプログラム ID に到着する成果物をランダムに割り当てます。 特定のプログラム ID を使用してメッセージを受信するリスナーのみにそのプログラム ID へのアクセスがあることを保証する必要があります、そのため、 さらに、SAP は、プログラム ID にアタッチされているリスナーに成果物をランダムに送信するため、はリスナーを 1 つのプログラム Id を専用にすることをお勧めします。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[SAP アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)