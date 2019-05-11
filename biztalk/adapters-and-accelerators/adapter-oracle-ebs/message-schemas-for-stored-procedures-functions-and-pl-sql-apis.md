---
title: ストアド プロシージャ、関数、および PL-SQL Api のメッセージ スキーマ |Microsoft Docs
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
ms.openlocfilehash: 518cdfa65b6083247784d37a2c49431f3631d9c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375396"
---
# <a name="message-schemas-for-stored-procedures-functions-and-plsql-apis"></a>ストアド プロシージャ、関数、PL/SQL Api のメッセージ スキーマ
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]サーフェス基になる Oracle データベースの操作としてストアド プロシージャ、関数、および PL/SQL Api (ストアド プロシージャおよびパッケージ内の関数)。 このセクションでは、メッセージの構造とストアド プロシージャ、関数、および PL/SQL Api の呼び出しに使用するアクションについて説明します。  
  
## <a name="message-structure-of-stored-procedures-functions-and-plsql-apis"></a>ストアド プロシージャ、関数、および PL/SQL Api のメッセージの構造  
 関数の操作が表示され、ストアド プロシージャが、要求-応答のメッセージ交換パターンに従います。 次の表では、これらの要求と応答メッセージの構造を示します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|操作|XML メッセージ|説明|  
|---------------|-----------------|-----------------|  
|ストアド プロシージャの要求|`<[SP_NAME] xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|メッセージの本文に Oracle IN および OUT IN パラメーターをサポートしています|  
|ストアド プロシージャの応答|`<[SP_NAME]Response xmlns="[VERSION]/Procedures/[SCHEMA]">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|メッセージの本文に Oracle OUT、IN OUT パラメーターをサポートしています|  
|関数の要求|`<[FN_NAME] xmlns="[VERSION]/Functions/[SCHEMA] ">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|メッセージの本文に Oracle IN および OUT IN パラメーターをサポートしています|  
|関数の応答|`<[FN_NAME]Response xmlns="[VERSION]/Functions/[SCHEMA]">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|メッセージの本文に Oracle OUT、IN OUT パラメーターをサポートしています<br /><br /> 関数の戻り値が返される、 \<[FN_NAME] 結果\>要素。 これは、応答メッセージの最初の要素です。 すべてのパラメーターの前に来ます。|  
|PL/SQL API の要求|`<[SP_NAME] xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|関数またはストアド プロシージャと同じ|  
|パッケージ化されたプロシージャまたは関数の応答|`<[SP_NAME]Response xmlns="[VERSION]/PackageApis/[SCHEMA]/[PACKAGE_NAME]/[SP_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|関数またはストアド プロシージャと同じ|  
  
 エンティティの説明  
  
 [バージョン] =http://schemas.microsoft.com/OracleEBS/2008/05します。  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。  
  
 [FN_NAME] を実行する関数を =たとえば、FN_GETID です。  
  
 [PRM1_NAME] = Oracle パラメーターの名前。 メッセージごとにサポートされているパラメーターの方向の [説明] 列を参照してください。  
  
 [PACKAGE_NAME] = を対象となるプロシージャまたは関数を含むパッケージの名前。  
  
 Oracle データベースでは、ストアド プロシージャおよび関数のオーバー ロードをサポートします。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]オーバー ロードされた各成果物のターゲット名前空間にはオーバー ロードの文字列を追加することによってこの機能をサポートしています。 この文字列の値は、2 番目のオーバー ロードの最初のオーバー ロードで"overload2""overload1"が。 次の例では、2 つのオーバー ロードされたストアド プロシージャのメッセージ構造を示します。  
  
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
  
## <a name="message-actions-of-stored-procedures-functions-and-plsql-apis"></a>ストアド プロシージャ、関数、および PL/SQL Api のメッセージのアクション  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]ストアド プロシージャ、関数、および PL/SQL API 操作の次のメッセージのアクションを使用します。  
  
> [!NOTE]
>  表の後は、エンティティの説明を参照してください。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|ストアド プロシージャの要求|プロシージャ/[スキーマ]/[SP_NAME]|プロシージャ/SCOTT/SP_INSERT|  
|ストアド プロシージャの応答|プロシージャ/[スキーマ]/[SP_NAME]/応答|プロシージャ、SCOTT、SP_INSERT/応答|  
|関数の要求|関数/[スキーマ]/[FN_NAME]|FN_GETID SCOTT/関数/|  
|関数の応答|関数/[スキーマ]/[FN_NAME]/応答|関数、SCOTT、FN_GETID/応答|  
|PL/SQL API の要求|[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]|SCOTT/Package/CUSTOMER/SP_INSERT|  
|ストアド プロシージャの応答をパッケージ化|[スキーマ]/Package/[PACKAGE_NAME]/[SP_NAME]/応答|SCOTT/Package/CUSTOMER/SP_INSERT/response|  
|パッケージ化された関数の要求|[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]|SCOTT/Package/CUSTOMER/FN_GETID|  
|パッケージ化された関数の応答|[スキーマ]/Package/[PACKAGE_NAME]/[FN_NAME]/応答|SCOTT/Package/CUSTOMER/FN_GETID/response|  
|ストアド プロシージャのオーバー ロードされた要求|[スキーマ]/Procedure/[SP_NAME]/[オーバー ロードする]|SCOTT/Procedure/SP_INSERT/overload1|  
|応答のストアド プロシージャをオーバー ロード|[スキーマ]/Procedure/[SP_NAME]/[オーバー ロード]/応答|SCOTT/Procedure/SP_INSERT/overload1/response|  
  
 エンティティの説明  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。  
  
 [FN_NAME] を実行する関数を =たとえば、FN_GETID です。  
  
 [PACKAGE_NAME] = を対象となるプロシージャまたは関数を含むパッケージの名前。  
  
 [オーバー ロード] = のオーバー ロードのパラメーター。 使用可能な値は、overload1 や overload2、です。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter for Oracle E-business Suite のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)