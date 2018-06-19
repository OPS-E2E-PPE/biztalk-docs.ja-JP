---
title: ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート |Microsoft ドキュメント
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
ms.openlocfilehash: 40bad547627669bb22a6b32f05d96c6c7b2f68c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215722"
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a>ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]ルート レベルの次の送信操作を公開します。  
  
-   **ExecuteNonQuery**: この操作を使用すると、複数の結果セットを取得する場合に、Oracle E-business Suite での任意の SQL ステートメントまたは PL/SQL ブロックを実行します。 この関数の入力パラメーターには、文字列パラメーター (PL/SQL ブロック全体を実行する) と (OutRefCursorNames) の文字列の配列が含まれます。 OutRefCursorNames で指定した各文字列の値は、出力と同じ名前を持つ REF CURSOR を返す PL/SQL ブロックの REF CURSOR のパラメーター名と見なされます。 この関数は、データセットの配列をある OUT パラメーター (OutRefCursors) も受け取ります。 データセットについては、Oracle のマニュアルを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538)です。 この操作の戻り値は整数データ型の影響を受けた行の数を示します。  
  
-   **ExecuteReader**: この操作を使用して、結果セットをデータセットとして指定する場合、Oracle E-business Suite で任意の SQL ステートメントや PL/SQL ブロックがあるを実行します。 この操作は、入力として文字列パラメーターを受け取り、データセットを返します。  
  
-   **ExecuteScalar**: この操作を使用して返される値を 1 つだけの場合に、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行します。 戻り値が結果セットの場合は、最初の行の最初の列の値だけが XML 文字列の形式で返されます。  
  
> [!NOTE]
>  -   ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作はユーザー定義型 (Udt) のサポートされていません。  
> -   内の ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作用のアプリケーションのコンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 Oracle E-business Suite (インターフェイス テーブル、ビューのインターフェイス、同時実行プログラムまたは要求内の成果物のターゲットが、操作のいずれかの場合に、ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のアプリケーション コンテキストを設定する必要が設定します)。 アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)