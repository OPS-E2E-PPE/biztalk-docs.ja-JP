---
title: "BizTalk Adapter for Siebel のバインドのプロパティについて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding properties, setting
- binding properties, adapter
- how to, set binding properties
ms.assetid: 48c77a2d-091c-40e0-aaf3-dc2ec34c55f2
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3237be098ea19fc7ff35770ddcb38a10d1e85c1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="read-about-biztalk-adapter-for-siebel-binding-properties"></a>BizTalk Adapter for Siebel のバインドのプロパティについてください。
[!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]を有効にすると、その実行時およびデザイン時の動作のいくつかを制御するいくつかのバインドのプロパティを表示します。 このセクションでは、これらのバインディング プロパティを説明し、設定する方法を説明するトピックへのリンクを示します。  
  
## <a name="the-siebel-adapter-binding-properties"></a>Siebel アダプターのバインドのプロパティ  
 次の表に、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]カテゴリにグループ化のプロパティをバインドします。 カテゴリは、各バインド プロパティがアダプター (またはバインド) を構成する別のアプリケーションによって表示されるダイアログ ボックスに表示されるノードを参照します。  
  
|プロパティのバインド|カテゴリ|Description|.NET 型|  
|----------------------|--------------|-----------------|---------------|  
|EnableBizTalkCompatibilityMode|全般|BizTalk 層チャネル バインド要素を読み込む必要があるかどうかを指定します。<br /><br /> これを設定して**True**をバインド要素を読み込めません。 それ以外の場合、これを設定して**False**です。<br /><br /> アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常にプロパティに設定する必要があります**True**です。 アダプターを使用するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、常にプロパティに設定する必要があります**False**です。|bool (System.Boolean)|  
|名前|全般|によって生成されたファイルの名前を指定、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]保持するために、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアント クラスです。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]フォームの値に、ファイル名の「クライアント」を追加することによって、**名前**プロパティの既定値は"SiebelBinding"以外の場合は、この値を生成されたファイルの名前"SiebelBindingClient"です。|string|  
|CloseTimeout|全般|指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]接続がタイムアウトを終了します。 既定値は 1 分です。|System.DateTime|  
|OpenTimeout|全般|指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]接続がタイムアウトを開きます。 既定値は 1 分です。|System.DateTime|  
|ReceiveTimeout|全般|指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージの受信タイムアウトします。 既定値は、10 分です。|System.DateTime|  
|SendTimeout|全般|指定します、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]メッセージ送信のタイムアウト。 既定値は 1 分です。|System.DateTime|  
|EnableConnectionPooling|接続|指定するかどうか、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続プールが有効にします。 既定値は**true**、接続プールが有効になっていることを指定します。|bool (System.Boolean)|  
|IdleConnectionTimeout|接続|指定します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アイドル接続のタイムアウト。 このタイムアウトを超える期間の接続がアイドル状態の接続が破棄されます。 既定値は 1 分です。|System.DateTime|  
|MaxConnectionsPerSystem|接続|内の接続の最大数を指定、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]接続プールします。 既定は 5 です。 **MaxConnectionsPerSystem**アプリケーション ドメイン内で静的なプロパティです。 つまり、変更すると、 **MaxConnectionsPerSystem**アプリケーション ドメインで 1 つのバインディング インスタンスの場合は、新しい値がそのアプリケーション ドメイン内のすべてのバインディング インスタンスから作成されたすべてのオブジェクトに適用されます。|int 型 (System.Int32)|  
|EnablePerformanceCounters|診断|指定するかどうか、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]パフォーマンス カウンターと[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]LOB の待機時間のパフォーマンス カウンターが有効になってです。 既定値は**true**; パフォーマンス カウンターが有効にします。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] LOB の待機時間のパフォーマンス カウンターが、アダプターが Siebel システムへの呼び出しで費やした合計時間を測定します。|bool (System.Boolean)|  
|ログデータ|診断|トレース内のビジネス データをキャプチャするかどうかを指定します。 既定値は**false**; ビジネス データはキャプチャされません。|bool (System.Boolean)|  
|AcceptCredentialsInUri|表示されません、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。|Siebel 接続 URI が Siebel システムのユーザーの資格情報を含めることができるかどうかを指定します。 既定値は**false**、接続 URI でユーザー資格情報を無効にします。 場合**AcceptCredentialsInUri**は**false** 、接続 URI には、ユーザーの資格情報が含まれています、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]例外をスローします。 設定することができます**AcceptCredentialsInUri**に**true**場合は、URI で資格情報を指定する必要があります。 詳細については、次を参照してください。 [Siebel システム接続 URI を作成する](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。|bool (System.Boolean)|  
  
## <a name="how-do-i-set-siebel-binding-properties"></a>Siebel のバインドのプロパティを設定する方法は?  
 Siebel システムへの接続を構成するときに、Siebel のバインドのプロパティを設定することができます。 バインドのプロパティを設定する方法についてはときにします。  
  
-   使用して、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]を参照してください[Visual Studio での Siebel システムへの接続](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないと、そのバインドのプロパティは、バインド ファイル (XML ファイル) または app.config ファイルでは使用できませんし、既定値が null の場合は、それぞれします。 必要があります手動で追加するバインディングのプロパティとその値をバインド ファイルまたは app.config ファイルに必要な場合です。  
  
-   送信ポートを構成するか、受信ポート (場所) で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューションを参照してください[Siebel するポートのバインド ファイルを使用する物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)です。
  
-   プログラミング ソリューションで、WCF チャネル モデルを使用して、参照してください[Siebel を使用して、チャネルの作成](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md)です。  
  
-   プログラミング ソリューションで WCF サービス モデルを使用して、参照してください[Siebel システムの WCF クライアントを構成する](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)です。  
  
-   使用する WCF ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を参照してください[BizTalk adapter 用 Siebel eBusiness Applications ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)です。  
  
## <a name="see-also"></a>参照  
[Siebel アプリケーションを開発します。](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)