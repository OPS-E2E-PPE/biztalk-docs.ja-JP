---
title: ストアド プロシージャ、関数、および PL-SQL Api のメッセージ スキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d707f10-470d-4390-bb5b-0301c326f375
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029c48c1e6066d09d43da51b2bb1f6786a516f54
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963152"
---
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a>ストアド プロシージャ、関数、および PL/SQL Api のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]サーフェス基になる Oracle データベースの操作としてストアド プロシージャ、関数、および PL/SQL Api (ストアド プロシージャ、およびパッケージ内の関数)。 このセクションでは、メッセージの構造とストアド プロシージャ、関数、および PL/SQL Api の呼び出しに使用する操作について説明します。  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a>ストアド プロシージャ、関数、および PL/SQL Api のメッセージの構造  
 関数の操作が表示され、ストアド プロシージャが、要求-応答メッセージ交換パターンに従います。 次の表は、これらの要求と応答メッセージの構造を示しています。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|ストアド プロシージャ要求|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|メッセージの本文に Oracle IN パラメーターおよび IN OUT パラメーターをサポートしています|  
|ストアド プロシージャの応答|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|メッセージの本文に Oracle OUT パラメーターとで OUT パラメーターをサポートしています|  
|関数の要求|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|メッセージの本文に Oracle IN パラメーターおよび IN OUT パラメーターをサポートしています|  
|関数の応答|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|メッセージの本文に Oracle OUT パラメーターとで OUT パラメーターをサポートしています<br /><br /> 関数の戻り値が返されます、 \<[FN_NAME] 結果\>要素。 これは、応答メッセージの最初の要素です。 すべてのパラメーターの前になります。|  
|PL/SQL API 要求|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|関数またはストアド プロシージャと同じ|  
|パッケージ化されたプロシージャまたは関数の応答|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|関数またはストアド プロシージャと同じ|  
  
 エンティティの説明  
  
 [バージョン] http://schemas.microsoft.com/OracleEBS/2008/05 を = です。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。  
  
 [FN_NAME] 実行する関数を =たとえば、FN_GETID です。  
  
 [PRM1_NAME] = Oracle パラメーターの名前。 メッセージごとにサポートされているパラメーターの方向について [説明] 列を参照してください。  
  
 [PACKAGE_NAME] を対象のプロシージャまたは関数を含むパッケージの名前を = です。  
  
 Oracle データベースでは、ストアド プロシージャと関数のオーバー ロードをサポートします。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]オーバー ロードされた各成果物のターゲット名前空間にオーバー ロード文字列を付加してこの機能をサポートします。 この文字列の値は"overload1"最初のオーバー ロード"overload2"の 2 番目のオーバー ロードです。 次の例は、2 つのオーバー ロードされたストアド プロシージャのメッセージ構造を示しています。  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
## <a name="message-actions-of-stored-procedures-functions-and-plsql-apis"></a>ストアド プロシージャ、関数、および PL/SQL Api のメッセージの動作  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ストアド プロシージャ、関数、および PL/SQL API 操作の次のメッセージ アクションを使用します。  
  
> [!NOTE]
>  表の後に、エンティティの説明を参照してください。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|ストアド プロシージャ要求|プロシージャ/[スキーマ]/[SP_NAME]|プロシージャ/SCOTT/SP_INSERT|  
|ストアド プロシージャの応答|プロシージャ/[スキーマ]/[SP_NAME]/応答|プロシージャ、SCOTT、SP_INSERT/応答|  
|関数の要求|機能/[スキーマ]/[FN_NAME]|FN_GETID SCOTT/関数/|  
|関数の応答|機能/[スキーマ]/[FN_NAME]/応答|関数、SCOTT、FN_GETID/応答|  
|PL/SQL API 要求|[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]|SCOTT/パッケージ/顧客/SP_INSERT|  
|ストアド プロシージャの応答をパッケージ化|[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]/応答|SCOTT/パッケージ/顧客/SP_INSERT/応答|  
|パッケージ化された関数の要求|[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]|SCOTT/パッケージ/顧客/FN_GETID|  
|パッケージ化された関数の応答|[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]/応答|SCOTT/パッケージ/顧客/FN_GETID/応答|  
|ストアド プロシージャのオーバー ロードされた要求|[スキーマ]/Procedure/[SP_NAME]/[オーバー ロードする]|SCOTT、プロシージャ、SP_INSERT/overload1|  
|ストアド プロシージャの応答をオーバー ロード|[スキーマ]/Procedure/[SP_NAME]/[オーバー ロード]/応答|SCOTT/プロシージャ/SP_INSERT/overload1/応答|  
  
 エンティティの説明  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。  
  
 [FN_NAME] 実行する関数を =たとえば、FN_GETID です。  
  
 [PACKAGE_NAME] を対象のプロシージャまたは関数を含むパッケージの名前を = です。  
  
 [オーバー ロード]、オーバー ロードのパラメーターを = です。 使用可能な値は overload1、overload2、およびなどです。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle E-Business Suite 用のメッセージとメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)