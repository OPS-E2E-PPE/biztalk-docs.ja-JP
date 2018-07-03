---
title: Oracle データベースでシノニムに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 608e8c36-ac78-4d7d-aca4-be552505fc2b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e782f5257658f9145bda3cabc67a306acf22f94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986067"
---
# <a name="operations-on-synonyms-in-oracle-database"></a>Oracle データベースでシノニムに対する操作
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]シノニムに対する操作を実行することができます。 シノニムは、別名またはフレンドリ名 (テーブル、ビュー、ストアド プロシージャ、関数、およびパッケージ) などのデータベース オブジェクトです。 Oracle のシノニムの詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=138058](http://go.microsoft.com/fwlink/?LinkId=138058)します。  
  
## <a name="advantages-of-using-synonyms"></a>シノニムを使用する利点  
 シノニムは、次のシナリオで役立ちます。  
  
-   **スキーマが異なる作業**: 別のスキーマ、およびスキーマ間でオブジェクトにアクセスする必要がある場合は、別の SQL ステートメントを使用して、それらのオブジェクトにアクセスする必要があります。 スキーマでオブジェクトのシノニムを作成でき、オブジェクトにアクセスする SQL ステートメントでシノニムを使用することができます。 別のスキーマ内の基になるオブジェクトにアクセスする必要がある場合は、別のスキーマ内のオブジェクト をポイントするシノニムの定義を変更します。 したがって、シノニムに基づくアプリケーションは、SQL ステートメントで変更しなくても機能し続けます。  
  
     たとえば、テスト、運用環境の同一の 2 つのスキーマがあるとします:"Test"、"Prod"。 使用する必要があります"Test"スキーマの"Employee"をという名前のテーブルにアクセスする`Test.Employee`または`Employee`("Test"が既定のスキーマの場合)、SQL ステートメントでします。 今すぐに使用する必要がある運用スキーマの"Employee"表を使用する場合は、`Prod.Employee`または`Employee`(既定のスキーマを"Prod"に変更する) SQL ステートメントでします。 この問題を回避するには、"Test.Employee"(たとえば"")、EMP テーブルのシノニムを作成し、SQL ステートメントで使用することができます。 "Prod.Employee"テーブルに対する操作を実行する必要がある場合は、"Prod.Employee"テーブルを指すように"EMP"のシノニムの定義を変更します。 これによりでさまざまなスキーマ オブジェクトに対して操作を実行する、SQL ステートメントを変更する必要はありません。  
  
-   **基になるオブジェクトの変更**: シノニム名または操作を実行している基になるオブジェクトの場所のすべての変更から動かします。 名前または基になるオブジェクトの場所のすべての変更に対応するシノニムの定義を変更することができます。  
  
     たとえば、ストアド プロシージャのいずれかでテーブルを使用するいるとします。 ここで、テーブル名の変更や、テーブルが別の場所に移動する場合、ストアド プロシージャ動作しなくなります。 この問題を回避するには、は、ストアド プロシージャ内のテーブルに対してシノニムを使用して名またはテーブルの場所に変更がある場合は、シノニムの定義を更新します。  
  
-   **簡素化されセキュリティで保護されたアクセス**: 分散環境では、適切なオブジェクトにアクセスしていることを確認するオブジェクト名と共にスキーマ名を使用する必要があります。 さらに、ユーザーがターゲット オブジェクトの権限を必要なことを確認する必要があります。 これを簡素化するには、オブジェクトへの完全修飾パスを含むシノニムを作成して、オブジェクトの簡易名を割り当てるし、シノニムに対する適切な特権を付与できます。  
  
## <a name="working-with-synonyms-in-the-adapter"></a>アダプターでのシノニムの使用  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] For Oracle でシノニムを公開します。  
  
- テーブル  
  
- ビュー  
  
- ストアド プロシージャ  
  
- 関数  
  
- パッケージ  
  
  内のそれぞれの基になるアーティファクトと共にこれらの成果物の各シノニムが公開されている、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 たとえば、**テーブル**スキーマの下のノードは、スキーマで、データベース テーブルとテーブルのすべてのシノニムを表示、**ビュー**に沿ったビューのすべてのシノニムがスキーマの下のノードに表示されますスキーマでデータベースのビュー。  
  
- テーブルおよびビューの作成、シノニムの同じ操作は、基になるテーブルとビューそれぞれ公開されます。 たとえば、基になるテーブルとビューが LOB 列を含む場合テーブルとビューのシノニムは ReadLOB と UpdateLOB 操作を公開も。  
  
- ストアド プロシージャ、関数、およびパッケージの作成、シノニムのシノニムは、それぞれの基になるストアド プロシージャ、関数、およびスキーマ内のパッケージと共に操作として公開されます。  
  
> [!NOTE]
>  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ローカル シノニムのみをサポートしています。 これは、それらのシノニムは、ローカル サーバー上のアイテムを対象とするアダプターでサポートされていることを意味します。  
  
 さらに、シノニムのメッセージ アクションでは、アクションが実行される成果物名以外の基になるオブジェクトと同じです。 メッセージのアクションなど、**選択**SCOTT スキーマ内のテーブルでの操作が:`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/[TABLE_NAME]/Select`します。 メッセージのアクションになりますし、SCOTT スキーマで、同じテーブルのシノニムでの選択操作を実行するかどうか:`http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/[SYNONYM_NAME]/Select`します。  
  
 アダプターでシノニムに対する操作を呼び出すと、アダプターは、操作を実行する Oracle データベースでシノニムを呼び出します。 ただし、アダプターは、メタデータを取得するのにシノニムの定義で、基になるオブジェクト名を使用します。  
  
 シノニムは、通常の送信操作、複合操作、およびポーリングで使用できます。  
  
> [!NOTE]
>  シノニムを検索できます[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]他のオブジェクトと同様です。 ただし、パッケージ内の手順を行うことができます、スキップするレベルのノードからシノニム パッケージ内の手順については検索できません。 アダプターでの操作の検索方法の詳細については、次を参照してください。[参照、検索、および Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)