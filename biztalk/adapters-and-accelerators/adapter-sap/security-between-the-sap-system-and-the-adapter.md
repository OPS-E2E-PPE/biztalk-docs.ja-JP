---
title: "SAP システムとアダプター間のセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1c0e37662b9c554d05b73ecf234da4b2ee547fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-sap-system-and-the-adapter"></a>SAP システムとアダプター間のセキュリティ
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] SAP セキュリティで保護されたネットワーク通信 (SNC) またはユーザー名パスワード資格情報、SAP サーバーとの間のセキュリティで保護された通信をサポートしています。 ユーザー名パスワードの資格情報は、SAP システムに接続の認証のみを提供します。接続経由で交換されるデータのすべてのセキュリティは提供されません。 SNC とユーザー名パスワードの資格情報を同時に使用することはできません。  
  
## <a name="sap-secure-network-communications"></a>SAP のセキュリティで保護されたネットワーク通信  
 セキュリティで保護されたネットワーク通信 (SNC) は、SAP クライアントと SAP アプリケーション サーバー間で交換されるデータでのアプリケーション レベルのセキュリティのために役立つ、SAP システムのアーキテクチャでのソフトウェア レイヤーです。  
  
 SNC には次の利点があります。  
  
-   SNC のターゲット アプリケーション レベル、エンド ツー エンド セキュリティです。 SNC は、2 つの SNC で保護されているコンポーネント (たとえばとの間、SAPgui が SAP システムのアプリケーション サーバー) 間のすべての通信をセキュリティ保護に役立ちます。  
  
-   (例でのシングル サインオンまたは認証にスマート カードを使用) の SAP システムを直接提供しない追加のセキュリティ機能を実装することができます。  
  
-   SNC 実装をカスタマイズすることができます。 任意のセキュリティ製品を使用し、使用するアルゴリズムを選択できます。  
  
-   セキュリティ製品は、SAP システムのビジネス アプリケーションに影響を与えずにいつでも変更できます。  
  
 SNC を使用するのには、SAP サーバーとを実行するクライアントの両方を構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   セキュリティで保護されたネットワーク通信 (SNC) は、SAP サーバーに構成します。 ガイダンスについては、SAP のマニュアルを参照してください。  
  
-   SAP クライアント Dll を持つコンピューター上および[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]をインストールする必要があります、SNC に関連する Dll です。 これらの Dll の詳細については、次を参照してください。、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] [ソフトウェアの前提条件](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)です。  
  
-   SNC の使用にアダプターを構成するのには、SAP 接続 URI で UseSnc パラメーターを設定する必要があります。 SAP 接続 URI の詳細については、次を参照してください。 [SAP アダプターの接続 URI の構成](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)です。 また、設定する必要があります、 **SncLibrary**と**SncPartnerName**プロパティをバインドします。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
## <a name="user-name-password-credentials"></a>ユーザー名パスワードの資格情報  
 接続 URI のアダプターにユーザー名パスワード資格情報を指定することができます。 アダプターでは、これらの資格情報を使用して、接続が開かれたときに、SAP システムのユーザーを認証します。 これらの資格情報をある程度の SAP システムへの接続の承認ただし、これらは提供しませんメッセージ レベルまたはトランスポート レベル認証 (承認) データをネットワーク上の移動します。  
  
 このためには、適切なレベルの承認、認証、データのプライバシー、およびアダプターと、SAP システムの間のデータ交換用のデータの整合性を確保するセキュリティ メカニズムを提供する必要があります。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、SAP システムの資格情報は、接続 URI で許可されているかどうかを判断します。 既定では、 **AcceptCredentialsInUri**が false と[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]URI に資格情報が含まれている場合に例外をスローします。 詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
 ネットワーク経由で複数のセキュリティを提供することの 1 つの可能なメカニズムは、インターネット プロトコル セキュリティ (IPsec) です。 IPsec は、オープン標準インターネット プロトコル (IP) ネットワーク経由で通信を保護するためのフレームワークです。  
  
 ユーザー名とパスワードはクリア テキストで、接続 URI として指定されます。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]はさまざまなメソッドを使用する、これらの資格情報を指定することがより安全に提供します。  
  
-   安全に BizTalk ソリューションで SAP システムの資格情報を提供する方法については、次を参照してください。 [SAP アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)です。  
  
-   安全にプログラミング ソリューションで SAP システムの資格情報を提供する方法については、次を参照してください。 [SAP アダプターをセキュリティで保護された使用したプログラミング](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md)です。  
  
## <a name="security-concerns-for-inbound-scenarios"></a>受信シナリオのセキュリティに関する注意事項  
 SAP プログラム ID へのアクセス権を持つすべてのリスナーがすべて SAP アイテム (Rfc、Idoc、および tRFCs) したプログラム ID に送信されるを受け取ることができます可能性があります。 プログラム ID を複数のリスナーを登録すると、SAP するときに、リスナーのいずれかにそのプログラム ID に到着した成果物はランダムに割り当てます。 特定のプログラム ID を使用してメッセージを受信するリスナーだけにそのプログラム ID へのアクセスがあることを保証する必要があります、そのため、 さらに、SAP は、プログラム ID にアタッチされているリスナーに成果物をランダムに送信するためは、プログラム Id を 1 つのリスナーに専用に使用することをお勧めします。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[SAP アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)