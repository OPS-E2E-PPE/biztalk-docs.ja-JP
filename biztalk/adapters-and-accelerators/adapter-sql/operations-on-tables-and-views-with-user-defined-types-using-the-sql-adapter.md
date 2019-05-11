---
title: SQL アダプターを使用してユーザー定義型を持つテーブルとビューに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4006bbe-91ca-4cd9-844d-5ed63142001f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb497a951230463e307a18ec6f12db69ab2c8da9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368623"
---
# <a name="operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter"></a>SQL アダプターを使用してユーザー定義型を持つテーブルとビューに対する操作
使用することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]テーブルまたはユーザー定義型 (Udt) 列を含むビューで操作を実行します。 標準のテーブル操作 (Insert、Update、Delete、および選択) を読み取り、または UDT 型の列にデータを書き込むを使用することができます。 このようなテーブルで、ストアド プロシージャおよび関数を実行することもできます。 ただし、アダプターを使用するには、UDT 列を含むテーブルを操作するには、特定のタスクを実行する必要があります。 これらのタスクを実行すると、アダプターを使用できます。  

-   説明に従って、Insert、Delete、Update、および Select の操作を実行[Insert、update、delete、または SQL アダプターを使用した BizTalk Server を使用して操作を選択します](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)します。  

-   ストアド プロシージャの実行」の説明に従って[BizTalk Server を使用して SQL Server でストアド プロシージャを実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)します。  

-   UDT 列、テーブルでの複合操作の実行」の説明に従って[BizTalk Server を使用して SQL Server での複合操作の実行](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)  

-   」の説明に従って、UDT 列を持つテーブルをポーリング[BizTalk Server を使用して SQL Server からのデータ変更メッセージの受信のポーリングに基づいた](../../adapters-and-accelerators/adapter-sql/receive-polling-based-data-changed-messages-from-sql-server-using-biztalk.md)します。  

-   説明に従って、その他の操作を実行[、BizTalk アプリケーションの開発](../../core/develop-your-biztalk-applications.md)します。  

## <a name="considerations-while-performing-operations-on-tables-with-udts"></a>Udt テーブルで操作を実行する場合の考慮事項  
 UDT 列を持つテーブルに対する操作を実行するアダプターを使用する前に、次のタスクを実行する必要があります。  

- **使用して操作のスキーマを生成するときに [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  


  |                       UDT 型                        |                                                                                                                                                                        アセンブリの場所                                                                                                                                                                        |
  |-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | たとえば、Geography の SQL Server に、Udt が付属  | ようにことを確認して Microsoft.SqlServer.Types.dll は GAC に追加してください。<br />-ことを確認して SqlServerSpatial.dll は、System32 フォルダーにあります。<br /><br /> コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。 |
  | SQL Server に付属していないが、ユーザーによって定義された Udt |                      同じ場所にある、Udt のそれぞれのアセンブリが使用できるように、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]実行可能ファイル devenv.exe します。 実行可能ファイルは通常、`<installation drive>:\Program Files\Microsoft Visual Studio <version>\Common7\IDE`します。                      |


- **使用して、操作を実行中に [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]**  


  |                       UDT 型                        |                                                                                                                                                                        アセンブリの場所                                                                                                                                                                        |
  |-------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | たとえば、Geography の SQL Server に、Udt が付属  | ようにことを確認して Microsoft.SqlServer.Types.dll は GAC に追加してください。<br />-ことを確認して SqlServerSpatial.dll は、System32 フォルダーにあります。<br /><br /> コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。 |
  | SQL Server に付属していないが、ユーザーによって定義された Udt |                                     Udt のそれぞれのアセンブリが 使用できるように、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]インストール場所。 BizTalk server では、通常、これは\<インストール ドライブ\>: \Program Files\Microsoft BizTalk Server です。                                      |


- **使用して、操作を実行中に [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]**  

  |UDT 型|アセンブリの場所|  
  |--------------|----------------------------|  
  |たとえば、Geography の SQL Server に、Udt が付属|ようにことを確認して Microsoft.SqlServer.Types.dll は GAC に追加してください。<br />-ことを確認して SqlServerSpatial.dll は、System32 フォルダーにあります。<br /><br /> コンピューターにこれらの Dll をインストールするには、SQL Server セットアップを実行し、選択**管理ツール-基本**と**管理ツール-完全**で、**機能の選択**ウィザードのページ。|  
  |SQL Server に付属していないが、ユーザーによって定義された Udt|通常、プロジェクトの \bin\Debug フォルダーの下にはプロジェクトの実行可能ファイルと同じ場所にある、Udt のそれぞれのアセンブリが使用できることを確認します。|  

  これらのタスクを完了すると、Udt を持つテーブルに対する操作を実行するすべての設定しています。  

## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)