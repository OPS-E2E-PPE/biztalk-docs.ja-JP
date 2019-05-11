---
title: チュートリアル 1:SQL アダプタを BizTalk プロジェクトの移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 889a09c99bc83060e4a2a60721a86fb5e21503e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367442"
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a>チュートリアル 1:SQL アダプタを BizTalk プロジェクトを移行します。
以前のバージョンを Microsoft に同梱されている SQL アダプターの[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]WCF ベースのとは異なる[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]など、多くの点で。  
  
- BizTalk プロジェクトの作成、デザイン時エクスペリエンス。  
  
- メタデータの取得エクスペリエンス。  
  
- スキーマ ファイル名と名前空間。  
  
- データ型のマッピング。  
  
- アダプターを使用して実行できる操作。  
  
- BizTalk Server 管理コンソールで物理ポートの構成  
  
  移行する BizTalk プロジェクト作成を使用して、前のバージョン、SQLadapter の内のトピックでは、これらの相違点がについて説明します。  
  
  ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
  このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。  
  
> [!NOTE]
>  説明を簡潔にするため、このチュートリアルでは以前のバージョンの SQL アダプターを vPrev SQL アダプターとして指す場合は。 同様に、vPrev SQL アダプタを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。  
> 
> [!IMPORTANT]
>  このチュートリアルでは、SQL Server データベースのテーブルの基本的な挿入操作を実行する vPrev SQL アダプター BizTalk プロジェクトを移行する方法のガイダンスを提供します。 このチュートリアルでは、新しい vPrev SQL アダプタからの移行に関するすべての考えられるシナリオについては説明しません WCF ベース[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 基盤として、この移行のチュートリアルを使用して、既存のプロジェクトに関連する変更を適宜変更する必要があります。  
  
## <a name="sample-used-for-the-tutorial"></a>このチュートリアルで使用されるサンプル  
 このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SQL_Migration) に基づいています。 Microsoft とサンプルが提供される[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、サンプルを参照してください。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、SQL Server データベースの Customer テーブルに対して挿入操作を実行する BizTalk プロジェクトが含まれます。 Customer テーブルには、次のデザインがあります。  
  
    |列名|説明|  
    |-----------------|-----------------|  
    |v_custid|プライマリ キーの整数型、id フィールド|  
    |名前|nchar(10) 型|  
  
-   VPrev SQL アダプターを使用して SQL Server データベースに対して、挿入操作を実行する要求メッセージが必要です。 要求メッセージは、vPrev SQL アダプタを使用して生成する挿入操作のスキーマに準拠している必要があります。  
  
-   」の手順を完了する必要があります[Before You 開発 BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)します。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**します。 これは、簡単なオーケストレーション ポート送信 WCF カスタムを使用して SQL Server データベースに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、ファイルの別の場所に保存します。  
  
-   **SQL Server データベースで実行する操作のスキーマを**します。 このチュートリアルには、顧客テーブルに挿入操作を実行する BizTalk プロジェクトが含まれます。 顧客テーブルに対して生成されたスキーマは、InsertCustomerService.xsd です。 VPrev SQL アダプターを使用して、このスキーマが生成されます。  
  
-   **要求メッセージ**します。 顧客テーブルに挿入操作を実行する要求メッセージ。 要求メッセージのスキーマは、SQL アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SQL アダプターによって生成されたスキーマに準拠している要求メッセージを送信するために、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]のスキーマ。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
- WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- WCF ベースを使用して挿入操作を実行するための要求メッセージに vPrev SQL アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]vPrev SQL アダプターの応答メッセージにします。  
  
- WCF カスタム SQL の作成でポートの送信、受信、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
- 要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: VPrev BizTalk プロジェクトを SQL アダプターを使用しての変更します。](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [手順 2:SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成します。](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [ステップ 3:SQL アダプタを使用する移行されたアプリケーションをテストします。](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a>参照  
 [SQL アダプターのチュートリアル](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)