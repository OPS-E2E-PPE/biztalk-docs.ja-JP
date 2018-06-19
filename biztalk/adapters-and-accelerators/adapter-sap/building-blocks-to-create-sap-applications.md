---
title: SAP アプリケーションを作成するビルド ブロック |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- design-time tasks
- run-time tasks
- developing, fundamentals of (BizTalk applications)
ms.assetid: 591a5597-5e7d-44b0-8bee-e1c987c5e6c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d507518b61b3c61b1815ec3ffe94bc1df5603d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218170"
---
# <a name="building-blocks-to-create-sap-applications"></a>SAP アプリケーションを作成する構成要素
使用して SAP システムの操作を実行する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アクティビティの 2 つのセットが含まれます: デザイン時および実行時のアクティビティ。 使用して SAP システムの操作を実行する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールをそれぞれします。 このセクションでは、これらのタスクの概要を示します。 すべてトピックでは、ここでは、SAP システムを使用して、特定の操作を実行する方法を示す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクでは、モデル化します。  
  
## <a name="design-time-tasks"></a>デザイン時のタスク  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]参照、検索、および Rfc、Bapi、およびを使用して XML スキーマ定義言語 (Xsd) の形式での Idoc を SAP メタデータを取得する機能を提供、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 Xsd は、SAP システムで実行する操作に固有のものと[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]は BizTalk プロジェクトを作成する場合にのみ使用できます。 デザイン時に、次のタスクを実行する必要があります。  
  
-   **BizTalk プロジェクトを作成し、スキーマ生成**です。 最初に、microsoft BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、SAP システムで呼び出すことが、RFC のスキーマを生成します。 たとえば、SAP システムで RFC_CUSTOMER_GET を呼び出す場合は、RFC_CUSTOMER_GET のメタデータを生成する必要があります。 このステップで使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成します。 詳細については、次を参照してください。 [Visual Studio での SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)です。  
  
-   **オーケストレーションを設定**です。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションの送信および受信と送信図形と受信論理ポートいます。 後の手順では、BizTalk Server 管理コンソールを使用して、物理ポートにこれらの論理ポートをマップします。 オーケストレーションでは、これらのポートを使用して、アダプター クライアントが送信するメッセージを選択します。 オーケストレーションは、SAP システムへのメッセージを渡します。 SAP システムからの応答が受信されると、オーケストレーションには、アダプターのクライアントに応答が渡されます。  
  
-   **メッセージを作成し、スキーマにリンク**です。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
-   **メッセージとポートにメッセージの構築図形をマップ**です。 オーケストレーションで 3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形にマップする必要があります。 そのメッセージを送信するポートをメッセージ図形をマップすることも必要があります。  
  
     たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形である場合は、要求メッセージと、要求メッセージを送信するポートをこの図形をマップします。  
  
-   **BizTalk プロジェクト ビルドおよび配置**です。 オーケストレーションを設定し、メッセージ、ポート、およびスキーマをマップした後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトを作成するため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルが必要です。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
    > [!NOTE]
    >  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
 ソリューションを展開した後、デザイン時のタスクが行われます。 実行時のタスクを実行する必要があります。  
  
## <a name="run-time-tasks"></a>実行時のタスク  
 実行時に、配置、およびデザイン時に作成されたオーケストレーションを監視する、BizTalk Server 管理コンソールを使用することができます。 さらに、行う必要があります。  
  
-   **アプリケーションを構成する**です。 オーケストレーションと BizTalk Server 管理コンソールでデザイン時に展開した BizTalk プロジェクトが表示されます。 物理ポートを使用して今すぐ作成する必要がありますをデザイン時に作成した論理ポートをマップすることによってこのオーケストレーションを構成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
     物理ポート、"action"または「アクション マッピング」を指定する必要があります。 この操作は、SAP システムで実行する操作に対応します。 動的なアクションを使用していない場合、アクションを設定する必要があります。 
  
-   **アプリケーションを起動**です。 アプリケーションを構成した後、アプリケーションを起動し、定義されているファイルの場所で入力メッセージを削除する必要があります。 オーケストレーションは、入力メッセージを使用し、SAP システムに渡し、応答を受信します。 この応答は別の定義済みのファイルの場所で使用可能になります。  
  
 これらの高度なデザイン時およびランタイムのタスクを行うため、また他のタスクを実行する必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続を SAP システムへの接続に URI を指定する必要があります。 このセクションの内容についての情報などの反復的なタスクを使用して BizTalk アプリケーションを開発するように実行する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SAP アダプターを BizTalk Server 管理コンソールに追加します。](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)  
  
-   [SAP アダプターの接続 URI を構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)  
  
-   [SAP システムの資格情報で、サインオンを構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md) 
  
-   [SAP アダプターのバインドのプロパティを構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)
  
-   [SAP システムの SOAP アクションを構成します。](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)
  
-   [SAP アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)
  
-   [SAP にポートのバインド ファイルを使用して物理ポートのバインドを構成します。](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)
  
-   [SAP アダプターの動的ポートを構成します。](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)
  
-   [SAP アダプターのバインドを再利用します。](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)
  
## <a name="see-also"></a>参照  
[SAP アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)