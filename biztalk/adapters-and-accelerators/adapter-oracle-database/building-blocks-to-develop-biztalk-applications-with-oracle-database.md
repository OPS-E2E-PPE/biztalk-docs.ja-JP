---
title: Oracle データベースと BizTalk アプリケーションを開発する基盤 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, BizTalk applications
- run-time tasks
- design-time tasks
ms.assetid: ad9ca856-5569-41ab-8617-ae6db5e3b4d7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0747569ef58e1f2223baefba6c51b77b205eb0d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214842"
---
# <a name="building-blocks-to-develop-biztalk-applications-with-oracle-database"></a>Oracle データベースと BizTalk アプリケーションを開発する構成要素
使用して Oracle データベースに対する操作の実行、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] 2 組タスクにはが含まれます: デザイン時および実行時。  
  
## <a name="design-time-tasks"></a>デザイン時のタスク  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]参照、検索、およびを使用して Oracle メタデータ テーブル、ストアド プロシージャ、および XML スキーマ定義言語 (Xsd) の形式でこのようなその他の項目を取得する機能を提供、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]です。 Xsd では、Oracle データベースで実行する操作に固有です。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]は BizTalk プロジェクトを作成する場合にのみ使用できます。 デザイン時に、次のタスクを実行する必要があります。  
  
-   **BizTalk プロジェクトを作成し、スキーマ生成**です。 Microsoft では、BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]し、Oracle データベースで実行される操作のスキーマを生成します。 たとえば、EMPLOYEE テーブルにレコードを挿入する場合は、EMPLOYEE テーブルに対して挿入操作のメタデータを生成する必要があります。 このステップで使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]スキーマを生成します。 詳細については、次を参照してください。 [Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)です。
  
-   **オーケストレーションを設定**です。 スキーマを生成した後、オーケストレーション デザイナーを使用してオーケストレーションを設定する必要があります。 基本的なオーケストレーションの送信および受信と送信図形と受信論理ポートいます。 後の手順では、BizTalk Server 管理コンソールを使用して、物理ポートにこれらの論理ポートをマップします。 オーケストレーションでは、これらのポートを使用して、アダプター クライアントが送信するメッセージを選択します。 オーケストレーションは、Oracle データベースにメッセージを渡します。 Oracle データベースからの応答が受信されると、オーケストレーションには、アダプターのクライアントに応答が渡されます。  
  
-   **メッセージを作成し、スキーマにリンク**です。 オーケストレーションでは、最初の手順で生成したスキーマにマップされるメッセージを作成する必要があります。 通常、要求メッセージと応答メッセージを作成します。 これらのメッセージは、対応する要求および応答スキーマにマップされます。  
  
-   **メッセージとポートにメッセージの構築図形をマップ**です。 オーケストレーションで 3 番目の手順で作成したメッセージを 2 番目の手順で追加した各図形にマップする必要があります。 そのメッセージを送信するポートをメッセージ図形をマップすることも必要があります。  
  
     たとえば、オーケストレーションの最初の図形がメッセージを受信する受信図形である場合は、要求メッセージと、要求メッセージを送信するポートをこの図形をマップします。  
  
-   **BizTalk プロジェクト ビルドおよび配置**です。 オーケストレーションとマップされたメッセージ、ポート、およびスキーマを設定したら、BizTalk ソリューションをビルドする必要があります。 プロジェクトを作成するため[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、アセンブリ キー ファイルを作成する必要があります。 ソリューションを正常にビルドした後は、ソリューションを配置する必要があります。  
  
    > [!NOTE]
    >  手順についてを含め、これらの高度なタスクの詳細については、このセクションのさまざまなトピックで提供されます。  
  
 ソリューションを展開した後、デザイン時のタスクが行われます。 実行時のタスクを実行する必要があります。  
  
## <a name="run-time-tasks"></a>実行時のタスク  
 実行時に、配置、およびデザイン時に作成されたオーケストレーションを監視する、BizTalk Server 管理コンソールを使用することができます。 さらに、行う必要があります。  
  
-   **アプリケーションを構成する**です。 オーケストレーションと BizTalk Server 管理コンソールでデザイン時に展開した BizTalk プロジェクトが表示されます。 BizTalk Server 管理コンソールを使用して今すぐ作成する必要がありますの物理ポートにデザイン時に作成した論理ポートをマップすることによって、このオーケストレーションを構成する必要があります。  
  
     物理ポート、"action"または「アクション マッピング」を指定する必要があります。 この操作は、Oracle データベースで実行する操作に対応します。 動的なアクションを使用していない場合、アクションを設定する必要があります。  
  
-   **アプリケーションを起動**です。 アプリケーションを構成した後、アプリケーションを起動し、定義されているファイルの場所で入力メッセージを削除する必要があります。 オーケストレーションは、入力メッセージを使用し、Oracle データベースに渡してと応答を受信します。 この応答は別の定義済みのファイルの場所で使用可能になります。  
  
 これらの高度なデザイン時およびランタイムのタスクを行うため、また他のタスクを実行する必要があります。 たとえば、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]スキーマを生成するには、接続を Oracle データベースに接続する URI を指定する必要があります。 このセクションの内容についての情報などの反復的なタスクを使用して BizTalk アプリケーションを開発するように実行する必要があります、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  

  
## <a name="see-also"></a>参照  
[Oracle データベース アダプターを使用して BizTalk アプリケーションを開発します。](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)