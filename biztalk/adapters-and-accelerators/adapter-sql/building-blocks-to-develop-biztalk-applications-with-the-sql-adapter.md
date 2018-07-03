---
title: SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac7cbf4-b111-43ad-8726-36d037918c9c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96095b0d0b7df8dfabee1ff2a1955008bd757182
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975491"
---
# <a name="building-blocks-to-develop-biztalk-applications-with-the-sql-adapter"></a>SQL アダプターを使用した BizTalk アプリケーションを開発する構成要素
使用して SQL Server での操作を実行する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールでそれぞれします。 このセクションでは、これらのタスクの概要を示します。 このセクションでを使用して SQL サーバーの特定の操作を実行する方法を示すすべてのトピック[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクをモデル化されます。  
  
## <a name="using-visual-studio"></a>Visual Studio の使用  
  
1. **BizTalk プロジェクトを作成し、スキーマの生成**します。 BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、し、SQL Server で実行する操作のスキーマを生成します。 たとえば、SQL Server テーブルにレコードを挿入する場合は、そのテーブルの挿入操作のスキーマを生成する必要があります。 スキーマを生成するには、使用する必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 詳細については、次を参照してください。 [SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)します。  
  
2. **オーケストレーションを設定**します。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションには、受信と送信図形とし、受信論理ポートの送信を追加します。 後の手順でマップするこれらの論理ポートを物理ポートを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 オーケストレーションでは、これらのポートを使用して、クライアントがアダプターから送信されるメッセージを選択します。 オーケストレーションは、SQL Server にメッセージを渡します。 SQL Server が応答を送信すると、オーケストレーションは、アダプターのクライアントに応答を渡します。  
  
3. **メッセージを作成し、スキーマにリンク**します。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
4. **メッセージとポートへのメッセージの構築図形のマップ**します。 オーケストレーションでは、3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形をマップする必要がありますようになりました。 そのメッセージを送信するポートをメッセージ図形をマップすることもあります。  
  
    たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形の場合は、要求メッセージと要求メッセージを送信するポートをこの図形をマップします。  
  
5. **BizTalk プロジェクト ビルドおよび配置**します。 オーケストレーションとマップされたメッセージ、ポート、およびスキーマを設定した後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトをビルドするため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルを作成する必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
> [!NOTE]
>  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
 正常にビルドし、BizTalk プロジェクトで、タスクを展開した後[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]行われます。 使用して特定のタスクを今すぐ実行する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
## <a name="using-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールの使用  
  
1. **アプリケーションを構成**します。 デプロイを使用した BizTalk プロジェクト[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]に表示されます、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーションとして、管理コンソール。 作成した論理ポートをマッピングすることによって、このオーケストレーションを構成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を物理ポートを使用して今すぐ作成する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
    物理ポートでは、"action"または「アクション マッピング」を指定する必要があります。 このアクションは、SQL Server で実行する操作に対応します。 動的アクションを使用していない場合は、アクションを指定する必要があります。 アクションの詳細については、次を参照してください。 [SQL アダプタの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)します。  
  
2. **アプリケーションを起動**します。 アプリケーションを構成した後、アプリケーションを起動し、定義済みのファイルの場所に要求メッセージを削除する必要があります。 オーケストレーションは、要求メッセージを使用し、SQL Server に渡します、応答を受信します。 この応答は、別の定義済みのファイルの場所のアダプター クライアントの使用可能です。  
  
   これらの高度なタスクを実現するには、その他のタスクを実行することも必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続を SQL Server に接続するための URI を指定する必要があります。 このセクションでは情報などの反復的なタスクを使用して BizTalk アプリケーションの開発に実行する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server 管理コンソールへの SQL アダプタの追加](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)  
  
-   [SQL アダプターの接続 URI を構成します。](../../adapters-and-accelerators/adapter-sql/configure-the-connection-uri-for-the-sql-adapter.md)  
  
-   [SQL アダプターの資格情報で、サインオンを構成します。](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)
  
-   [SQL アダプタのバインドのプロパティを構成します。 ](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md) 
  
-   [SQL アダプタの SOAP アクションを構成します。 ](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)
  
-   [SQL アダプターを物理ポートのバインドを手動で構成します。 ](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md) 
  
-   [SQL アダプターを使用するポートのバインド ファイルを使用して物理的なポート バインドを構成します。](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)
  
-   [動的なポートの構成](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)
  
-   [アダプター バインドの再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)
  
## <a name="see-also"></a>参照  
[BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)