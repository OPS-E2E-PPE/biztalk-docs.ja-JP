---
title: "Oracle E-business Suite アプリケーションを作成するビルド ブロック |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 483a52d4-1aaf-46b1-bb42-9f91bf678346
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0450f672573153df803f875a0dbac1436f8f4760
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-create-oracle-e-business-suite-applications"></a>Oracle E-business Suite アプリケーションを作成する構成要素
使用して Oracle E-business Suite での操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールをそれぞれします。 このセクションでは、これらのタスクの概要を示します。 すべてトピックでは、ここでは、Oracle E-business Suite を使用して上の特定の操作を実行する方法を示す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクでは、モデル化します。  
  
## <a name="using-visual-studio"></a>Visual Studio の使用  
  
1.  **BizTalk プロジェクトを作成し、スキーマ生成**です。 BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、Oracle E-business Suite でを実行する操作のスキーマを生成します。 たとえば、Oracle E-business Suite のインターフェイス テーブルからレコードを選択する場合は、そのテーブルに対して Select 操作のスキーマを生成する必要があります。 スキーマを生成するには、使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]です。 詳細については、次を参照してください。 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)です。  
  
2.  **オーケストレーションを設定**です。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションの送信および受信と送信図形と受信論理ポートいます。 後の手順でマップするこれらの論理ポートを物理ポートを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 オーケストレーションでは、これらのポートを使用して、アダプター クライアントが送信するメッセージを選択します。 オーケストレーションは、Oracle E-business Suite にメッセージを渡します。 Oracle E-business Suite では、応答を送信、オーケストレーションは、アダプターのクライアントへの応答を渡します。  
  
3.  **メッセージを作成し、スキーマにリンク**です。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
4.  **メッセージとポートにメッセージの構築図形をマップ**です。 オーケストレーションで 3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形にマップする必要があります。 そのメッセージを送信するポートをメッセージ図形をマップすることも必要があります。  
  
     たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形である場合は、要求メッセージと、要求メッセージを送信するポートをこの図形をマップします。  
  
5.  **BizTalk プロジェクト ビルドおよび配置**です。 オーケストレーションとマップされたメッセージ、ポート、およびスキーマを設定したら、BizTalk ソリューションをビルドする必要があります。 プロジェクトを作成するため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルを作成する必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
> [!NOTE]
>  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
 内のデザイン時のタスクが正常にビルドし、BizTalk プロジェクトを展開した、いったん[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]行われます。 使用して特定の実行時タスクを実行する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
## <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールを使用します。  
  
1.  **アプリケーションを構成する**です。 使用して、展開した BizTalk プロジェクト[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に現れる、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションとして管理コンソールです。 作成した論理ポートをマップすることによってこのオーケストレーションを構成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を物理ポートを使用して今すぐ作成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
     物理ポート、"action"または「アクション マッピング」を指定する必要があります。 この操作は、Oracle E-business Suite に対して実行する操作に対応します。 動的なアクションを使用していない場合は、操作を指定する必要があります。 アクションの詳細については、次を参照してください。 [for Oracle E-business Suite SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)です。  
  
2.  **アプリケーションを起動**です。 アプリケーションを構成した後、アプリケーションを起動し、定義済みのファイルの場所に要求メッセージを削除する必要があります。 オーケストレーション要求のメッセージを使用するには、Oracle E-business Suite に渡しておよび応答を受信します。 この応答は、別の定義ファイルの場所にあるクライアントがアダプターで使用可能です。  
  
 これらの高度なタスクを行うため、また他のタスクを実行する必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続を Oracle E-business Suite への接続に URI を指定する必要があります。 このセクションの内容についての情報などの反復的なタスクを使用して BizTalk アプリケーションを開発するように実行する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server 管理コンソールへの Oracle E-business Suite アダプターの追加](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)  
  
-   [For Oracle E-business Suite 接続 URI の構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite のサインイン資格情報を構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite のバインド プロパティを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite の SOAP アクションを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business アダプターにバインドする物理ポートを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
-   [Oracle E-business Suite へのポートのバインド ファイルを使用して物理ポートのバインドを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)  
  
-   [Oracle E-business Suite で動的ポートを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-dynamic-ports-with-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite でアダプターのバインドを再利用します。](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの開発](../../core/developing-biztalk-server-applications.md)