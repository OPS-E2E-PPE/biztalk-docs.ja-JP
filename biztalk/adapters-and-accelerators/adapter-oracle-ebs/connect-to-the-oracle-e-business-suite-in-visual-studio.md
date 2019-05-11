---
title: Visual Studio で Oracle E-business Suite への接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e290ea7e-03f3-49d4-9f18-1e539d727d9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d98aaf7f2a8f377f9369e7e446f95c964e3f9db7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375590"
---
# <a name="connect-to-the-oracle-e-business-suite-in-visual-studio"></a>Visual Studio で Oracle E-business Suite への接続します。
このセクションを使用する方法について説明します、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
- **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)します。  
  
- **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 使用する、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、次を参照してください。 [BizTalk Server アプリケーションの開発](../../core/developing-biztalk-server-applications.md)します。  
  
  > [!NOTE]
  >  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公開される WCF カスタム バインドおよび BizTalk アダプターとして、いずれかを使用できる、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]Oracle E-business Suite に接続するための BizTalk プロジェクトから。  
  
- **[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** は非 BizTalk プログラミング プロジェクトで使用できます。 使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルを使用したソリューションの開発に関する詳細については、次を参照してください。 [WCF サービス モデルを使用して Oracle E-business Suite の開発アプリケーション](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)します。  
  
  使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、まず、Oracle E-business Suite に接続する必要があります。 3 つのメソッドは、以下を設定して接続を構成するダイアログ ボックスを表示します。  
  
- **接続パラメーター**します。 これらは、接続 URI の構築に使用されるパラメーターです。 データ ソース (Oracle net サービス名) を指定する必要があります。  
  
- **Oracle E-business suite ユーザー名パスワード資格情報**します。 これらは、接続の確立には、Oracle E-business Suite で、認証に使用されます。 ユーザー名とパスワードを指定する必要があります。  
  
  > [!IMPORTANT]
  >  この段階では、Oracle E-business Suite または基になる Oracle データベースの資格情報を指定できます。 接続し、メタデータを生成するには、資格情報を指定できます。 ただし、Oracle E-business Suite の成果物を呼び出す操作を実行中に、アプリケーションのコンテキストを呼び出したい Oracle E-business Suite のアプリケーションを設定する必要があるため Oracle E-business Suite の資格情報を指定する必要があります。 アプリケーション コンテキストの設定の詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
- **バインドのプロパティ**します。 バインドのプロパティは、操作のメタデータの生成中にはデザイン時に、これはオプションです。 バインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
  少なくとも、Oracle データベースへの接続を構成するときにのみ指定する必要がバインドのプロパティおよび接続を確立するために必要な接続パラメーターによって返されるメタデータに影響を与える、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]の操作ターゲットにします。 ただし、追加のバインドのプロパティと実行時に使用される接続パラメーターの値を指定する場合がありますもします。 これは、ためにです。  
  
- [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]バインドのプロパティと、接続を構成するときに指定する接続パラメーターから BizTalk ポートのバインド ファイルを作成し、このファイルをプロジェクトに追加します。 後で、このバインド ファイルを使用してでポートを作成することができます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 バインド ファイルの詳細については、次を参照してください。 [Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
- [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]バインドのプロパティと、接続を構成するときに指定する接続のプロパティから app.config ファイルを作成し、プロジェクト ディレクトリにこのファイルを追加します。  
  

- [Add Adapter Service Reference のプラグインを使用して Visual Studio での Oracle E-business Suite への接続します。](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-service-reference.md)  
  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)