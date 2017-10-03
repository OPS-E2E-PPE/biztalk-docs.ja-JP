---
title: "SQL アダプターを使用して SQL Server でストアド プロシージャを実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245626a7-f546-4aca-90df-c0579139a872
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65a475d8de1fc30df2e06923ad14bcba0897159e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="execute-stored-procedures-in-sql-server-using-the-sql-adapter"></a>SQL アダプターを使用して SQL Server でのストアド プロシージャの実行します。
Transact SQL と CLR ストアド プロシージャの SQL Server での操作として表示された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]下にある、**プロシージャ**ノードを使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 によって公開される操作名、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のストアド プロシージャの名前と同じです。 ストアド プロシージャ内のすべてのパラメーターは、対応する操作で公開されます。 OUT パラメーターには、ストアド プロシージャの戻り値が含まれています。 ストアド プロシージャの結果セットは、データセットの配列です。 データセットの詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=196853](http://go.microsoft.com/fwlink/?LinkId=196853)です。 ターゲット オブジェクトのスキーマ情報は、実行時に、応答メッセージの一部として取得されます。  
  
 ただし、デザイン時にターゲット オブジェクトのスキーマ情報を取得する場合は、プロシージャのスキーマを生成する必要があります、 **Strongly-Typed プロシージャ**内のノード、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 同じストアド プロシージャが下に表示されたに注意してください、**プロシージャ**と**Strongly-Typed プロシージャ**ノード。 ストアド プロシージャの戻り値は厳密に型指定とだけでなくデータセットの配列。 デザイン時に、スキーマ情報が利用できるようには、ストアド プロシージャのスキーマを別の操作を別のスキーマにマップを使用できます。 たとえば、データベース テーブルに対する挿入操作の生成スキーマを厳密に型指定されたプロシージャの生成スキーマをマップできます。  
  
> [!NOTE]
>  場合、厳密に型指定されたストアド プロシージャのデザイン時にスキーマ情報を表示することはできません。  
>   
>  -   厳密に型指定されたストアド プロシージャの入力パラメーターとして別のストアド プロシージャの戻り値であるカーソルを使用しています。  
> -   CLR ストアド プロシージャ、テーブルに対して何らかの操作を実行することをお勧めします。  
  
## <a name="support-for-stored-procedures-with-for-xml-clause"></a>FOR XML 句を含むストアド プロシージャのサポート  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を FOR XML 句を伴う SELECT ステートメントを持つストアド プロシージャを実行することもできます。 行セットではなく XML として結果を返す SELECT ステートメントで FOR XML 句を使用するとします。 FOR XML 句の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=131402](http://go.microsoft.com/fwlink/?LinkId=131402)です。  
  
> [!NOTE]
>  「ネイティブ」[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で利用可能な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サポート XML を返すプロシージャが格納されているもののみつまり、ある FOR XML 句、SELECT ステートメントでします。 FOR XML 句を使用してストアド プロシージャのサポート、WCF ベースを使用してこれらのストアド プロシージャを実行できる[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャの定義に変更を加えずにします。  
  
## <a name="support-for-stored-procedures-with-temporary-tables"></a>一時テーブルを持つストアド プロシージャのサポート  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]をその定義内の一時テーブルを含むストアド プロシージャのメタデータを生成することができます。 ただし、このようなストアド プロシージャの必要がありますを生成するメタデータをストアド プロシージャからのみを選択すると、**プロシージャ**を使用しているときに、ノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 アダプターがこのようなストアド プロシージャからのメタデータの生成をサポートしていません、 **Strongly-Typed プロシージャ**ノード。  
  
## <a name="support-for-result-sets-containing-columns-without-names-or-with-same-names"></a>名前のない、または同じ名前を持つ列を含む結果セットのサポート  
 次の表にリスト方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]名とストアド プロシージャと厳密に型指定されたストアド プロシージャの結果セット内の同じ名前のない列を処理します。  
  
|結果セットが含まれています.|ストアド プロシージャ|厳密に型指定されたストアド プロシージャ|  
|--------------------------|----------------------|--------------------------------------|  
|**名前のない列**|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次のように、列の名前が生成されます: せず、列の一意の ID (GUID) が生成される"-"(ハイフン)、その GUID 文字列がプレフィックス付きの"C"によって生成された GUID が数字で開始可能性がありますが、XML タグ名ができないためです。|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]列の次の名前が生成されます:"[column_index] UnNamedColumn"、column_index が '0' からを開始します。|  
|**同じ名前の列**|1 つ目以外の列の名前は「_」(アンダー スコア) なしのランダムな GUID で後に追加されます"-"(ハイフン)。 例:"\_[GUID]"です。|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]結果セットに同じ名前の列をサポートしておらず、例外をスローします。 **重要:**結果セット内の列名は、一意の名前であることを確認する必要があります。|  
  
> [!NOTE]
>  一般に、ストアド プロシージャの結果内のすべての列の設定し、ストアド プロシージャの厳密に型指定された名前する必要がありますで一意の名前を持っていることをお勧めします。  
  
 詳細については。  
  
-   ストアド プロシージャを実行する方法[BizTalk Server を使用して SQL Server でストアド プロシージャを実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)です。  
  
-   FOR XML 句を持つストアド プロシージャを実行する方法[BizTalk Server を使用して SQL Server での FOR XML 句を持つストアド プロシージャを実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)です。  
  
-   メッセージのストアド プロシージャのスキーマを参照してください[プロシージャと関数のメッセージ スキーマを](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)です。  
  
## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)