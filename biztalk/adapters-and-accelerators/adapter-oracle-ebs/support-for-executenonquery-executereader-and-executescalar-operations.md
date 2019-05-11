---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afdd1a5b-2a6b-48b8-a659-afd81f43f34b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30669e4f055e6a9783b87d78e774944370421b70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374527"
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、executescalar 操作をサポートします。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]ルート レベルで次の送信操作を公開します。  
  
-   **ExecuteNonQuery**:複数の結果セットを取得する場合に、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行するのにには、この操作を使用します。 この関数の入力パラメーターには、文字列パラメーター (実行全体の PL/SQL ブロック) および (OutRefCursorNames) 文字列の配列が含まれます。 OutRefCursorNames で指定した各文字列値は、出力と同じ名前を持つ REF CURSOR を返す PL/SQL ブロックの REF CURSOR のパラメーター名と見なされます。 この関数は、データセットの配列である OUT パラメーター (OutRefCursors) も受け取ります。 データセットの詳細についてでの Oracle のマニュアルを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538)します。 この操作の戻り値が整数データ型の影響を受けた行の数を示します。  
  
-   **ExecuteReader**:結果セットをデータセットとして指定する場合に、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行するのにには、この操作を使用します。 この操作は、入力として文字列パラメーターを受け取り、データセットを返します。  
  
-   **ExecuteScalar**:返される値の 1 つだけの場合、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行するのにには、この操作を使用します。 結果セットを戻り値には、XML 文字列の形式で、最初の行の最初の列の値だけが返されます。  
  
> [!NOTE]
> - ExecuteNonQuery、ExecuteReader、executescalar 操作はユーザー定義型 (Udt) のサポートされていません。  
>   - ExecuteNonQuery、ExecuteReader、executescalar 操作のアプリケーションのコンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 Oracle E-business Suite (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムまたは要求内のアイテムに対象が、操作のいずれかの場合は、ExecuteNonQuery、ExecuteReader、executescalar 操作のアプリケーション コンテキストを設定する必要があります。セットの場合)。 アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)