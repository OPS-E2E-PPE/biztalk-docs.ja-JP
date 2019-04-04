---
title: Oracle E-business Suite のアプリケーションを作成する構成要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 483a52d4-1aaf-46b1-bb42-9f91bf678346
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b615f5a1e021a0db1d9dcc4b5780a8e6c55a547c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013147"
---
# <a name="building-blocks-to-create-oracle-e-business-suite-applications"></a>Oracle E-business Suite のアプリケーションを作成する構成要素
使用して Oracle E-business Suite での操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールでそれぞれします。 このセクションでは、これらのタスクの概要を示します。 このセクションでの Oracle E-business Suite を使用して特定の操作を実行する方法を示すすべてのトピック[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクをモデル化されます。  
  
## <a name="using-visual-studio"></a>Visual Studio の使用  
  
1. **BizTalk プロジェクトを作成し、スキーマの生成**します。 BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、Oracle E-business Suite で実行する操作のスキーマを生成します。 たとえば、Oracle E-business Suite のインターフェイス テーブルからレコードを選択する場合は、そのテーブルの選択操作のスキーマを生成する必要があります。 スキーマを生成するには、使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 詳細については、[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)を参照してください。  
  
2. **オーケストレーションを設定**します。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションには、受信と送信図形とし、受信論理ポートの送信を追加します。 後の手順でマップするこれらの論理ポートを物理ポートを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 オーケストレーションでは、これらのポートを使用して、クライアントがアダプターから送信されるメッセージを選択します。 オーケストレーションは、Oracle E-business Suite へのメッセージを渡します。 Oracle E-business Suite では、応答を送信、オーケストレーションは、アダプターのクライアントに応答を渡します。  
  
3. **メッセージを作成し、スキーマにリンク**します。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
4. **メッセージとポートへのメッセージの構築図形のマップ**します。 オーケストレーションでは、3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形をマップする必要がありますようになりました。 そのメッセージを送信するポートをメッセージ図形をマップすることもあります。  
  
    たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形の場合は、要求メッセージと要求メッセージを送信するポートをこの図形をマップします。  
  
5. **BizTalk プロジェクト ビルドおよび配置**します。 オーケストレーションとマップされたメッセージ、ポート、およびスキーマを設定した後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトをビルドするため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルを作成する必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
> [!NOTE]
>  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
 内のデザイン時のタスクとビルドし、BizTalk プロジェクトをデプロイできました、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]行われます。 今すぐを使用して特定のランタイムのタスクを実行する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. **アプリケーションを構成**します。 デプロイを使用した BizTalk プロジェクト[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に表示されます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションとして、管理コンソール。 作成した論理ポートをマッピングすることによって、このオーケストレーションを構成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を物理ポートを使用して今すぐ作成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
    物理ポートでは、"action"または「アクション マッピング」を指定する必要があります。 このアクションは、Oracle E-business Suite で実行する操作に対応します。 動的アクションを使用していない場合は、アクションを指定する必要があります。 アクションの詳細については、[for Oracle E-business Suite の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)を参照してください。  
  
2. **アプリケーションを起動**します。 アプリケーションを構成した後、アプリケーションを起動し、定義済みのファイルの場所に要求メッセージを削除する必要があります。 オーケストレーション要求メッセージを使用するには、Oracle E-business Suite に渡しますおよび応答を受信します。 この応答は、別の定義済みのファイルの場所のアダプター クライアントの使用可能です。  
  
   これらの高度なタスクを実現するには、その他のタスクを実行することも必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続を Oracle E-business Suite に接続するための URI を指定する必要があります。 このセクションでは情報などの反復的なタスクを使用して BizTalk アプリケーションの開発に実行する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server 管理コンソールへの Oracle E-business Suite アダプターの追加](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)  
  
-   [For Oracle E-business Suite 接続 URI の構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business suite のサインイン資格情報を構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite のバインド プロパティを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business Suite の SOAP アクションを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)  
  
-   [Oracle E-business アダプターにバインドする物理ポートを手動で構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
-   [Oracle E-business Suite へのポートのバインド ファイルを使用して物理ポートのバインドを構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)  
  
-   [Oracle E-business Suite での動的ポートの構成します。](../../adapters-and-accelerators/adapter-oracle-ebs/configure-dynamic-ports-with-oracle-e-business-suite.md)  
  
-   [Oracle E-business suite アダプターのバインドを再利用します。](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの開発](../../core/developing-biztalk-server-applications.md)