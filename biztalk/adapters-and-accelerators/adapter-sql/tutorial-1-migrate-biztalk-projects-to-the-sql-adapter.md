---
title: "チュートリアル 1: SQL アダプタを BizTalk プロジェクトの移行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ca17095841fb154be9ec34766a34f174414cd82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a>チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。
以前のバージョンを Microsoft に同梱されている SQL アダプターの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF ベースとは異なります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]など、多くの点で。  
  
-   デザイン時に、BizTalk プロジェクトを作成する操作。  
  
-   メタデータの取得エクスペリエンス。  
  
-   スキーマ ファイル名と名前空間。  
  
-   データは、マッピングを入力します。  
  
-   アダプターを使用して実行できる操作です。  
  
-   BizTalk Server 管理コンソールで物理ポートの構成  
  
 これらの相違点については、移行する BizTalk プロジェクトを作成前のバージョンの使用、SQLadapter 内のトピックで説明します。  
  
 ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
 このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。  
  
> [!NOTE]
>  ここでは簡略化のため、このチュートリアルでは、SQL アダプターの以前のバージョンを vPrev SQL アダプターと呼びます。 同様に、vPrev SQL アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。  
  
> [!IMPORTANT]
>  このチュートリアルでは、SQL Server データベース テーブルの基本的な挿入操作を実行する vPrev SQL アダプター BizTalk プロジェクトを移行する方法について説明します。 このチュートリアルでは新しい vPrev SQL アダプタからの移行に関するすべての可能なシナリオについては説明しません WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 基盤としてこの移行のチュートリアルを使用して、既存のプロジェクトに関連する変更を加えるを適宜変更する必要があります。  
  
## <a name="sample-used-for-the-tutorial"></a>チュートリアルでは、使用されるサンプル  
 このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SQL_Migration) に基づいています。 サンプルが付属して Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、サンプルを参照してください。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、SQL Server データベースの Customer テーブルに対して挿入操作を実行する BizTalk プロジェクトが含まれます。 Customer テーブルには、次のデザインがあります。  
  
    |列名|Description|  
    |-----------------|-----------------|  
    |v_custid|主キー、整数型、id フィールド|  
    |名前|nchar(10) 型|  
  
-   要求メッセージを vPrev SQL アダプターを使用して SQL Server データベースで挿入操作を実行する必要があります。 要求メッセージは、vPrev SQL アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。  
  
-   内の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)です。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**です。 これは、ポートの Wcf-custom を使用して SQL Server データベースに要求メッセージの送受信送信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。  
  
-   **SQL Server データベースで実行する操作のスキーマ**です。 このチュートリアルには、顧客テーブルに Insert 操作を実行する BizTalk プロジェクトが含まれます。 顧客テーブルに対して生成されたスキーマは、InsertCustomerService.xsd です。 このスキーマは、vPrev SQL アダプターを使用して生成されます。  
  
-   **要求メッセージ**です。 顧客テーブルに挿入操作を実行する要求メッセージ。 要求メッセージのスキーマは、SQL アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SQL アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。 そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のスキーマです。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
-   WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev SQL アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]vPrev SQL アダプタの応答メッセージにします。  
  
-   WCF カスタム SQL を作成する送信の受信ポートの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
-   要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: vPrev SQL アダプターを使用して BizTalk プロジェクトを変更します。](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [手順 3: SQL アダプターを使用する移行されたアプリケーションをテストします。](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a>参照  
 [SQL アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)