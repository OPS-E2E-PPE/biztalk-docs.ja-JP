---
title: Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing BizTalk applicatons, run-time tasks
- developing BizTalk applications, design-time tasks
ms.assetid: 76204181-18ad-43b5-b589-539aafd66835
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e457ec1eb3b3c79ef1fc1a4618bb6a0ef37755d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981971"
---
# <a name="building-blocks-to-create-biztalk-applications-with-the-siebel-adapter"></a>Siebel アダプターを使用した BizTalk アプリケーションを作成する構成要素
Siebel システムを使用して操作を実行する[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アクティビティの 2 つのセットが含まれます: デザイン時および実行時のアクティビティ。 使用して Siebel システムの操作を実行する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、デザイン時および実行時のタスクのセットを実行する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]と[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールでそれぞれします。 このセクションでは、これらのタスクの概要を示します。 このセクションでを使用して Siebel システムに対して特定の操作を実行する方法を示すすべてのトピック[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、これらの高度なタスクをモデル化されます。  
  
## <a name="design-time-tasks"></a>デザイン時のタスク  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]参照、検索、および Siebel ビジネス コンポーネントとビジネス サービスを使用して XML スキーマ定義言語 (Xsd) の形式でメタデータを取得する機能を提供、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。 Xsd は、Siebel システムで実行する操作に固有と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]は BizTalk プロジェクトを作成する場合にのみ使用できます。 デザイン時に、次のタスクを実行する必要があります。  
  
- **BizTalk プロジェクトを作成し、スキーマ生成**します。 最初に、Microsoft で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]とビジネス コンポーネントまたは Siebel システムで呼び出すことがビジネス サービスのスキーマを生成します。 たとえば、アカウントのビジネス コンポーネントにレコードを挿入する場合は、アカウント ビジネス コンポーネントの挿入操作のメタデータを生成する必要があります。 この手順で使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成します。 詳細については、次を参照してください。 [Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)します。  
  
- **オーケストレーションを設定**します。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションには、受信と送信図形とし、受信論理ポートの送信を追加します。 後の手順では、BizTalk Server 管理コンソールを使用してこれらの論理ポートを物理ポートにマップします。 オーケストレーションでは、これらのポートを使用して、クライアントがアダプターによって送信されたメッセージを取得します。 オーケストレーションは、Siebel システムへのメッセージを渡します。 Siebel システムからの応答が受信されると、オーケストレーションは、アダプターのクライアントへの応答を渡します。  
  
- **メッセージを作成し、スキーマにリンク**します。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求と応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
- **メッセージとポートへのメッセージの構築図形のマップ**します。 オーケストレーションでは、3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形をマップする必要がありますようになりました。 そのメッセージを送信するポートをメッセージ図形をマップすることもあります。  
  
   たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形の場合は、「要求」のメッセージと要求メッセージを送信するポートをこの図形がマップされます。  
  
- **BizTalk プロジェクト ビルドおよび配置**します。 オーケストレーションを設定し、メッセージ、ポート、およびスキーマをマップした後は、BizTalk ソリューションをビルドする必要があります。 プロジェクトをビルドするため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルは必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
  > [!NOTE]
  >  これらの高レベルのタスクの説明の詳細は手順に関する情報を含む以下のトピックで提供されます。  
  
  ソリューションをデプロイすると、デザイン時のタスクが実現します。 実行時のタスクを実行する必要があります。  
  
## <a name="run-time-tasks"></a>実行時のタスク  
  
- **アプリケーションを構成**します。 デザイン時に展開した BizTalk プロジェクトは、オーケストレーションとして BizTalk Server 管理コンソールで表示されます。 BizTalk Server 管理コンソールを使用して今すぐ作成する必要がある物理ポートにデザイン時に作成した論理ポートをマッピングすることによって、このオーケストレーションを構成する必要があります。  
  
   物理ポートでは、"action"または「アクション マッピング」を指定する必要があります。 このアクションは、Siebel システムで実行する操作に対応します。 動的アクションを使用していない場合は、アクションを設定する必要があります。 
  
- **アプリケーションを起動**します。 アプリケーションを構成した後、アプリケーションを起動し、定義ファイルの場所で入力メッセージを削除する必要があります。 オーケストレーションは、入力メッセージを使用し、Siebel システムに渡しますと応答を受信します。 この応答は別の定義済みのファイルの場所で使用可能になります。  
  
  これらの高度なデザイン時およびランタイム タスクを実現するには、その他のタスクを実行することも必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]スキーマを生成するには、接続、Siebel システムへの接続に URI を指定する必要があります。 このセクションでは情報などの反復的なタスクを使用して BizTalk アプリケーションの開発に実行する必要があります、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
