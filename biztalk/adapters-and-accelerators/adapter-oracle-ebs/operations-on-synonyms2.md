---
title: Synonyms2 に対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bc9b2c4-ac22-491b-bc64-95e08a39b74d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce3de4d9c1010449c3f56cf2b47579dcc0210351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375305"
---
# <a name="operations-on-synonyms"></a>シノニムに対する操作
[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]シノニムに対する操作を実行することができます。 シノニムは、別名またはフレンドリ名 (テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージ) などのデータベース オブジェクトです。 Oracle のシノニムの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=138058](http://go.microsoft.com/fwlink/?LinkId=138058)します。  
  
## <a name="advantages-of-using-synonyms"></a>シノニムを使用する利点  
 シノニムは、次のシナリオで役立ちます。  
  
-   **スキーマが異なる作業**:異なるスキーマを使用してスキーマ間でオブジェクトにアクセスする必要がある場合に、これらのオブジェクトにアクセスする別の SQL ステートメントを使用する必要があります。 スキーマでオブジェクトのシノニムを作成でき、オブジェクトにアクセスする SQL ステートメントでシノニムを使用することができます。 別のスキーマ内の基になるオブジェクトにアクセスする必要がある場合は、別のスキーマ内のオブジェクト をポイントするシノニムの定義を変更します。 したがって、シノニムに基づくアプリケーションは、SQL ステートメントで変更しなくても機能し続けます。  
  
     たとえば、テスト、運用環境の同一の 2 つのスキーマがあるとします。"Test"、"Prod" 使用する必要があります"Test"スキーマの"Employee"をという名前のテーブルにアクセスする`Test.Employee`または`Employee`("Test"が既定のスキーマの場合)、SQL ステートメントでします。 今すぐに使用する必要がある運用スキーマの"Employee"表を使用する場合は、`Prod.Employee`または`Employee`(既定のスキーマを"Prod"に変更する) SQL ステートメントでします。 この問題を回避するには、"Test.Employee"(たとえば"")、EMP テーブルのシノニムを作成し、SQL ステートメントで使用することができます。 "Prod.Employee"テーブルに対する操作を実行する必要がある場合は、"Prod.Employee"テーブルを指すように"EMP"のシノニムの定義を変更します。 これによりでさまざまなスキーマ オブジェクトに対して操作を実行する、SQL ステートメントを変更する必要はありません。  
  
-   **基になるオブジェクトの変更**:シノニムは、名前または操作を実行している基になるオブジェクトの場所のすべての変更から隔離します。 名前または基になるオブジェクトの場所のすべての変更に対応するシノニムの定義を変更することができます。  
  
     たとえば、ストアド プロシージャのいずれかでテーブルを使用するいるとします。 ここで、テーブル名の変更や、テーブルが別の場所に移動する場合、ストアド プロシージャ動作しなくなります。 この問題を回避するには、は、ストアド プロシージャ内のテーブルに対してシノニムを使用して名またはテーブルの場所に変更がある場合は、シノニムの定義を更新します。  
  
-   **簡素化されセキュリティで保護されたアクセス**:分散環境では、適切なオブジェクトにアクセスしていることを確認するのにオブジェクト名と共にスキーマ名を使用することにあります。 さらに、ユーザーがターゲット オブジェクトの権限を必要なことを確認する必要があります。 これを簡素化するには、オブジェクトへの完全修飾パスを含むシノニムを作成して、オブジェクトの簡易名を割り当てるし、シノニムに対する適切な特権を付与できます。  
  
## <a name="working-with-synonyms-in-the-adapter"></a>アダプターでのシノニムの使用  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] For Oracle でシノニムを公開します。  
  
- テーブル  
  
- ビュー  
  
- ストアド プロシージャ  
  
- 関数  
  
- パッケージ  
  
  内のそれぞれの基になるアーティファクトと共にこれらの成果物の各シノニムが公開されている、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 たとえば、**テーブル**ノードの下、**ビューのスキーマに基づく**スキーマで、データベース テーブルとテーブルのすべてのシノニムを表示、**ビュー**ノードの下、**ビューのスキーマに基づく**しスキーマで、データベース ビューとビューのすべてのシノニムが表示されます。  
  
- テーブルおよびビューの作成、シノニムの同じ操作は、基になるテーブルとビューそれぞれ公開されます。 たとえば、基になるテーブルとビューが LOB 列を含む場合これらのテーブルとビューの類義語でも公開されます、Read_\<LOBColName\>と Update_\<LOBColName\>テーブルのシノニムを操作Read_\<LOBColName\>ビュー シノニムを操作します。  
  
- ストアド プロシージャ、関数、およびパッケージの作成、シノニムのシノニムは、それぞれの基になるストアド プロシージャ、関数、およびスキーマ内のパッケージと共に操作として公開されます。  
  
> [!NOTE]
>  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ローカル シノニムのみをサポートしています。 これは、それらのシノニムは、ローカル サーバー上のアイテムを対象とするアダプターでサポートされていることを意味します。  
  
 さらに、シノニムのメッセージ アクションでは、アクションが実行される成果物名以外の基になるオブジェクトと同じです。 メッセージのアクションなど、**選択**SCOTT スキーマ内のテーブルでの操作が:`Tables/Select/SCOTT/[TABLE_NAME]`します。 メッセージのアクションになりますし、SCOTT スキーマで、同じテーブルのシノニムでの選択操作を実行するかどうか:`Tables/Select/SCOTT/[SYNONYM_NAME]`します。  
  
 アダプターでシノニムに対する操作を呼び出すと、アダプターは、操作を実行する Oracle データベースでシノニムを呼び出します。 ただし、アダプターは、メタデータを取得するのにシノニムの定義で、基になるオブジェクト名を使用します。  
  
 シノニムは、通常の送信操作、複合操作、およびポーリングで使用できます。  
  
> [!NOTE]
>  シノニムを検索できます[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]他のオブジェクトと同様です。 ただし、パッケージ内の手順を行うことができます、スキップするレベルのノードからシノニム パッケージ内の手順については検索できません。 アダプターでの操作の検索方法の詳細については、次を参照してください。[参照、検索、および SQL アダプターを使用して SQL 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)