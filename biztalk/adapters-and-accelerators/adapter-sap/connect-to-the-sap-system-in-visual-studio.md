---
title: Visual Studio での SAP システムへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- Add Adapter Service Reference Visual Studio Plug-in
- Consume Adapter Service BizTalk Project Add-in
ms.assetid: 5fc356b1-05e8-4235-bb04-5ef6192c5291
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78aa28705c552ed037758247b2cb829bf8c9c2fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373638"
---
# <a name="connect-to-the-sap-system-in-visual-studio"></a>Visual Studio での SAP システムへの接続します。
このセクションを使用する方法について説明します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** は BizTalk Server プロジェクトで使用できます。 使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** は BizTalk Server プロジェクトで使用できます。 使用する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。  
  
  > [!NOTE]
  >  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]SAP システムに接続するための BizTalk プロジェクトから。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は非 BizTalk プログラミング プロジェクトで使用できます。 使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルを使用したソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して開発の SAP アプリケーション](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)します。  
  
  使用する、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]最初の SAP システムに接続する必要があります。 すべての 3 つのユーザー インターフェイスは、以下を設定して接続を構成するダイアログ ボックスを表示します。  
  
- **接続パラメーター**します。 これらは、アプリケーション サーバーのホストまたはメッセージ サーバーのホストとクライアント ID などの接続 URI の構築に使用されるパラメーター  
  
- **SAP システムのユーザー名パスワード資格情報**します。 これらは、接続の確立には、SAP システムで、認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
- **バインドのプロパティ**します。 バインドのプロパティは省略可能と指定するかどうかによって異なります主に特定のバインディング プロパティの設定を必要とする操作を対象にするかどうか。 たとえば、ReceiveIdoc 操作を設定する必要が、 **ReceiveIdocFormat**プロパティを文字列にバインドします。 バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
  少なくとも、SAP システムへの接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]操作します。対象にします。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定する場合がありますもします。 これは、ためにです。  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティとの接続を構成し、このファイルをプロジェクトに追加を指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成します。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティとの接続を構成し、プロジェクト ディレクトリでこのファイルを追加します。 指定した接続のプロパティから app.config ファイルを作成します。  
  

  
## <a name="see-also"></a>参照  
 [Visual Studio で SAP 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)