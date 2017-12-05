---
title: "SQL アダプターを使用してユーザー定義の型とテーブルとビューでの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4006bbe-91ca-4cd9-844d-5ed63142001f
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa05cf28e267e84dd73ad1a3ffd753ee89febb71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter"></a>SQL アダプターを使用してユーザー定義の型とテーブルとビューでの操作
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]テーブルまたはユーザー定義型 (Udt) 列を含むビューの操作を実行します。 標準のテーブルの操作 (Insert、Update、Delete、および選択) に UDT 型の列にデータを読み書きするを使用することができます。 このようなテーブルでストアド プロシージャと関数を実行することもできます。 ただし、UDT 列を含むテーブルを操作するために、アダプターを使用する前に、特定のタスクを実行する必要があります。 これらのタスクを実行すると、アダプターを使用できます。  
  
-   説明に従って、挿入、削除、更新、および Select の操作を行う[Insert、update、delete、または BizTalk Server アダプターを使用して、SQL select 操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)です。  
  
-   ストアド プロシージャの実行」の説明に従って[BizTalk Server を使用して SQL Server でストアド プロシージャを実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)です。  
  
-   説明に従って、UDT 列を含むテーブルに複合操作を行う[BizTalk Server を使用して SQL Server での複合操作を実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  
  
-   」の説明に従って、UDT 列を含むテーブルをポーリング[BizTalk Server を使用して SQL Server からのデータ変更メッセージの受信のポーリングに基づく](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)です。  
  
-   説明に従って、他の操作を行う[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)です。  
  
## <a name="considerations-while-performing-operations-on-tables-with-udts"></a>Udt を持つテーブルの操作を実行するときの考慮事項  
 UDT 列を持つテーブルの操作を実行するアダプターを使用する前に、次のタスクを実行する必要があります。  
  
-   **使用して操作のスキーマを生成するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  
  
    |UDT 型|アセンブリの場所|  
    |--------------|----------------------------|  
    |たとえば、Geography の SQL Server に、Udt が付属|ようにことを確認して Microsoft.SqlServer.Types.dll は GAC に追加してください。<br />-確認 SqlServerSpatial.dll は System32 フォルダーで使用できます。<br /><br /> SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。|  
    |SQL Server に付属していないが、ユーザーが定義した Udt|同じ場所に、それぞれ、Udt のアセンブリを利用できるように、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]実行可能ファイル devenv.exe です。 実行可能ファイルは通常`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`です。|  
  
-   **使用して、操作を実行するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]**  
  
    |UDT 型|アセンブリの場所|  
    |--------------|----------------------------|  
    |たとえば、Geography の SQL Server に、Udt が付属|ようにことを確認して Microsoft.SqlServer.Types.dll は GAC に追加してください。<br />-確認 SqlServerSpatial.dll は System32 フォルダーで使用できます。<br /><br /> SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。|  
    |SQL Server に付属していないが、ユーザーが定義した Udt|Udt のそれぞれのアセンブリを 利用できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]インストール場所。 BizTalk server では、通常、これは\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。|  
  
-   **使用して、操作を実行するときに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  
  
    |UDT 型|アセンブリの場所|  
    |--------------|----------------------------|  
    |たとえば、Geography の SQL Server に、Udt が付属|ようにことを確認して Microsoft.SqlServer.Types.dll は GAC に追加してください。<br />-確認 SqlServerSpatial.dll は System32 フォルダーで使用できます。<br /><br /> SQL Server セットアップを実行しを選択すると、コンピューターにこれらの Dll をインストールできます**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページです。|  
    |SQL Server に付属していないが、ユーザーが定義した Udt|Udt のそれぞれのアセンブリは、通常は、プロジェクトの \bin\Debug フォルダーの下にあるプロジェクトの実行可能ファイルと同じ場所で利用することを確認します。|  
  
 これらのタスクを完了すると、すべてのセットの Udt をテーブルに対して操作を実行しています。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)