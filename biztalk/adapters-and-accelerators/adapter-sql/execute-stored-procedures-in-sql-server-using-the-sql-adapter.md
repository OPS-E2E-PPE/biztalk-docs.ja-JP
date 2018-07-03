---
title: SQL アダプターを使用して SQL Server でのストアド プロシージャの実行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245626a7-f546-4aca-90df-c0579139a872
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6515baa313fc6b68c62556ad5b5883500cfde8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021555"
---
# <a name="execute-stored-procedures-in-sql-server-using-the-sql-adapter"></a>SQL アダプターを使用して SQL Server でのストアド プロシージャの実行します。
Transact SQL と CLR ストアド プロシージャの SQL Server での操作として表示された[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]下、**プロシージャ**ノードを使用しているときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 によって公開される操作名、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] SQL Server のストアド プロシージャの名前と同じです。 ストアド プロシージャ内のすべてのパラメーターは、対応する操作で公開されます。 OUT パラメーターには、ストアド プロシージャの戻り値が含まれています。 ストアド プロシージャの結果セットは、データセットの配列です。 データセットの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=196853](http://go.microsoft.com/fwlink/?LinkId=196853)します。 ターゲット オブジェクトのスキーマ情報は、実行時に、応答メッセージの一部として取得されます。  

 ただし、デザイン時にターゲット オブジェクトのスキーマ情報を取得する場合は、プロシージャのスキーマを生成する必要があります、 **Strongly-Typed プロシージャ**内のノード、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 同じストアド プロシージャが下に表示されるメモ、**プロシージャ**と**Strongly-Typed プロシージャ**ノード。 ストアド プロシージャの戻り値は、厳密に型指定とだけでなくデータセットの配列。 スキーマ情報は、デザイン時に、としては、ストアド プロシージャのスキーマを別の操作を別のスキーマにマップするのに使用できます。 たとえば、データベース テーブルに対する挿入操作の生成されたスキーマを厳密に型指定されたプロシージャの生成されたスキーマをマップできます。  

> [!NOTE]
>  場合は、厳密に型指定されたストアド プロシージャのデザイン時にスキーマ情報を表示することはできません。  
> 
> - 別のストアド プロシージャの戻り値を厳密に型指定されたストアド プロシージャの入力パラメーターとしては、カーソルを使用しています。  
>   -   テーブルにいくつかの操作を実行する CLR ストアド プロシージャになります。  

## <a name="support-for-stored-procedures-with-for-xml-clause"></a>FOR XML 句を使用したストアド プロシージャのサポート  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を FOR XML 句を使用した SELECT ステートメントを持つストアド プロシージャを実行することもできます。 SELECT ステートメントでは、FOR XML 句を使用して行セットではなく、結果を XML として返します。 FOR XML 句の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=131402](http://go.microsoft.com/fwlink/?LinkId=131402)します。  

> [!NOTE]
>  「ネイティブ」[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]で使用可能な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サポート XML を返すプロシージャが格納されているものは、資格のあるしか FOR XML 句、SELECT ステートメントでします。 WCF ベースを使用してこれらのストアド プロシージャを実行する FOR XML 句を使用したストアド プロシージャのサポート、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]ストアド プロシージャの定義に変更を加えずにします。  

## <a name="support-for-stored-procedures-with-temporary-tables"></a>一時テーブルとストアド プロシージャのサポート  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]一時テーブルでは、定義を含むストアド プロシージャのメタデータを生成することができます。 ただし、このようなストアド プロシージャにする必要がありますを生成するメタデータからのみ、ストアド プロシージャを選択して、**プロシージャ**を使用しているときに、ノード、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 アダプターがこのようなストアド プロシージャの下にあるメタデータの生成をサポートしていません、 **Strongly-Typed プロシージャ**ノード。  

## <a name="support-for-result-sets-containing-columns-without-names-or-with-same-names"></a>名前のない、または同じ名前を持つ列を含む結果セットのサポート  
 次の表方法、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]名およびストアド プロシージャと厳密に型指定されたストアド プロシージャの結果セット内の同じ名前のない列を処理します。  


|    結果セットが含まれています.     |                                                                                                                                                       ストアド プロシージャ                                                                                                                                                       |                                                                                                           厳密に型指定されたストアド プロシージャ                                                                                                            |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  **名前のない列**  | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次のように、列の名前が生成されます: なしの列の一意の ID (GUID) が生成された"-"(ハイフン)、その GUID 文字列が"C"でというプレフィックスが生成された GUID が数字で開始可能性がありますが、XML タグ名のことはできませんし。 |                                [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]列の名前が生成されます:"[column_index] UnNamedColumn"、'0' から column_index の開始位置。                                |
| **同じ名前の列** |                                                                                1 つ目以外の列の名前が付きます"*"(アンダー スコア) が続くことがなく、ランダムな GUID"-"(ハイフン)。例:"\\*[GUID]"。                                                                                | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]結果セットには、同じ名前の列をサポートしておらず、例外をスローします。 **重要:** 結果セット内の列名は、一意の名前であることを確認する必要があります。 |

> [!NOTE]
>  一般に、ストアド プロシージャの結果内のすべての列の設定し、ストアド プロシージャの厳密に型指定された名前付けする必要がありますで一意の名前を持っていることをお勧めします。  

 詳細については。  

-   ストアド プロシージャを実行する方法[BizTalk Server を使用して SQL Server でストアド プロシージャを実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)します。  

-   FOR XML 句を含むストアド プロシージャを実行する方法[BizTalk Server を使用して SQL Server での FOR XML 句を含むストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-having-a-for-xml-clause-in-sql-server-using-biztalk.md)します。  

-   メッセージのストアド プロシージャのスキーマを参照してください[プロシージャと関数のメッセージ スキーマ](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)します。  

## <a name="see-also"></a>参照  
 [アダプターを使用して SAP システムへの接続します。](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)