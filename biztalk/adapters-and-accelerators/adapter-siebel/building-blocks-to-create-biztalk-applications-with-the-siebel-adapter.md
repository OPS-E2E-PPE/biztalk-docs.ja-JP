---
title: "Siebel アダプターと BizTalk アプリケーションを作成するビルド ブロック |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing BizTalk applicatons, run-time tasks
- developing BizTalk applications, design-time tasks
ms.assetid: 76204181-18ad-43b5-b589-539aafd66835
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dea8fc354c3187ef7613ac35850b9408a05a9c0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-create-biztalk-applications-with-the-siebel-adapter"></a>Siebel アダプターと BizTalk アプリケーションを作成する構成要素
Siebel システムを使用して、上の操作を実行する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アクティビティの 2 つのセットが含まれます: デザイン時および実行時のアクティビティ。 使用して、Siebel システムに対して操作を実行する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールをそれぞれします。 このセクションでは、これらのタスクの概要を示します。 すべてトピックでは、ここでは、Siebel システムを使用して、特定の操作を実行する方法を示す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクでは、モデル化します。  
  
## <a name="design-time-tasks"></a>デザイン時のタスク  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]参照、検索、および Siebel ビジネス コンポーネントとビジネス サービスを使用して XML スキーマ定義言語 (Xsd) の形式でメタデータを取得する機能を提供、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 Xsd は、Siebel システムで実行する操作に固有のものと[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]は BizTalk プロジェクトを作成する場合にのみ使用できます。 デザイン時に、次のタスクを実行する必要があります。  
  
-   **BizTalk プロジェクトを作成し、スキーマ生成**です。 最初に、microsoft BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、ビジネス コンポーネントまたは Siebel システムで呼び出すことがビジネス サービスのスキーマを生成します。 たとえば、ビジネス コンポーネントをアカウントにレコードを挿入する場合は、アカウント ビジネス コンポーネントの挿入操作のメタデータを生成する必要があります。 このステップで使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成します。 詳細については、次を参照してください。 [Siebel 操作の Visual Studio でのメタデータを取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)です。  
  
-   **オーケストレーションを設定**です。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションの送信および受信と送信図形と受信論理ポートいます。 後の手順でこれらの論理ポートを BizTalk Server 管理コンソールを使用して物理ポートにマップされます。 オーケストレーションでは、これらのポートを使用して、アダプター クライアントによって送信されたメッセージを取得します。 オーケストレーションは、Siebel システムへのメッセージを渡します。 Siebel システムの応答が受信されると、オーケストレーションには、アダプターのクライアントに応答が渡されます。  
  
-   **メッセージを作成し、スキーマにリンク**です。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求と応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
-   **メッセージとポートにメッセージの構築図形をマップ**です。 オーケストレーションで 3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形にマップする必要があります。 そのメッセージを送信するポートをメッセージ図形をマップすることも必要があります。  
  
     たとえば、オーケストレーション内の最初の図形がメッセージを受信する受信図形である場合は、「要求」メッセージと、要求メッセージを送信するポートをこの図形がマップされます。  
  
-   **BizTalk プロジェクト ビルドおよび配置**です。 オーケストレーションを設定し、メッセージ、ポート、およびスキーマをマップした後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトを作成するため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルが必要です。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
    > [!NOTE]
    >  詳細についてはこの高度なタスクの説明、手続き型の情報を含むは、以下のトピックで提供されます。  
  
 ソリューションを展開した後は、デザイン時のタスクが行われます。 実行時のタスクを実行する必要があります。  
  
## <a name="run-time-tasks"></a>実行時のタスク  
  
-   **アプリケーションを構成する**です。 デザイン時に展開した BizTalk プロジェクトは、オーケストレーション BizTalk Server 管理コンソールで表示されます。 BizTalk Server 管理コンソールを使用して今すぐ作成する必要がありますの物理ポートにデザイン時に作成した論理ポートをマップすることによって、このオーケストレーションを構成する必要があります。  
  
     物理ポート、"action"または「アクション マッピング」を指定する必要があります。 この操作は、Siebel システムに対して実行する操作に対応します。 動的なアクションを使用していない場合、アクションを設定する必要があります。 
  
-   **アプリケーションを起動**です。 アプリケーションを構成した後、アプリケーションを起動し、定義されているファイルの場所で入力メッセージを削除する必要があります。 オーケストレーションは、入力メッセージを使用し、Siebel システムに渡し、応答を受信します。 この応答は別の定義済みのファイルの場所で使用可能になります。  
  
 これらの高度なデザイン時およびランタイムのタスクを行うため、また他のタスクを実行する必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続、Siebel システムへの接続に URI を指定する必要があります。 このセクションの内容についての情報などの反復的なタスクを使用して BizTalk アプリケーションを開発するように実行する必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。  
  
