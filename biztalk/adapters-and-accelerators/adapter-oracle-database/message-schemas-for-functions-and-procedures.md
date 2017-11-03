---
title: "メッセージ関数およびプロシージャのスキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functions and procedures, message structure of
- functions and procedures, message actions of
ms.assetid: 90b77b15-a4c6-487d-a09e-a078ceddfd1e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85585945ae6376e11ddc39e7a1280f69d024c439
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-functions-and-procedures"></a>関数およびプロシージャのメッセージ スキーマ
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェス Oracle データベースの関数およびストアド プロシージャを操作として。 このセクションでは、メッセージの構造と関数およびプロシージャの呼び出しに使用する操作について説明します。  
  
## <a name="message-structure-of-functions-and-procedures"></a>関数およびプロシージャのメッセージの構造  
 関数の操作が表示され、ストアド プロシージャが、要求-応答メッセージ交換パターンに従います。 次の表は、これらの要求と応答メッセージの構造を示しています。  
  
|操作|XML メッセージ|Description|  
|---------------|-----------------|-----------------|  
|ストアド プロシージャ要求|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|メッセージの本文に Oracle IN パラメーターおよび IN OUT パラメーターをサポートしています|  
|ストアド プロシージャの応答|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure">   <[PRM1_NAME]>value1<[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|メッセージの本文に Oracle OUT パラメーターとで OUT パラメーターをサポートしています|  
|関数の要求|`<[FN_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[FN_NAME]>`|メッセージの本文に Oracle IN パラメーターおよび IN OUT パラメーターをサポートしています|  
|関数の応答|`<[FN_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function">   <[FN_NAME]Result>return_value</[FN_NAME]Result>   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   …    </[FN_NAME]Response>`|メッセージの本文に Oracle OUT パラメーターとで OUT パラメーターをサポートしています<br /><br /> 関数の戻り値が返されます、 \<[FN_NAME] 結果 > 要素。 これは、応答メッセージの最初の要素です。 すべてのパラメーターの前になります。|  
|パッケージ化されたプロシージャまたは関数の要求|`<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]>`|関数またはストアド プロシージャと同じ|  
|パッケージ化されたプロシージャまたは関数の応答|`<[SP_NAME]Response xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]">   <[PRM1_NAME]>value1</[PRM1_NAME]>   <[PRM2_NAME]>value2</[PRM2_NAME]>   … </[SP_NAME]Response>`|関数またはストアド プロシージャと同じ|  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。  
  
 [FN_NAME] 実行する関数を =たとえば、FN_GETID です。  
  
 [PRM1_NAME] = Oracle パラメーターの名前。 メッセージごとにサポートされているパラメーターの方向について [説明] 列を参照してください。  
  
 [PACKAGE_NAME] を対象のプロシージャまたは関数を含むパッケージの名前を = です。  
  
 Oracle データベースでは、ストアド プロシージャと関数のオーバー ロードをサポートします。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]オーバー ロードされた各成果物のターゲット名前空間にオーバー ロード文字列を付加してこの機能をサポートします。 この文字列の値は"overload1"最初のオーバー ロード"overload2"の 2 番目のオーバー ロードです。 次の例は、2 つのオーバー ロードされたストアド プロシージャのメッセージ構造を示しています。  
  
```  
Stored Procedure Overload 1:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload1">    
  <[PRM1_NAME]>value1</[PRM1_NAME]>  
  <[PRM2_NAME]>value1</[PRM2_NAME]>  
  …  
</[SP_NAME]>  
  
Stored Procedure Overload 2:  
<[SP_NAME] xmlns="http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/overload2">    
  <[PRM1_NAME]>value1</I_[PRM1_NAME]>  
  <[PRM2_NAME]>value1</I_[PRM2_NAME]>  
  …  
</[SP_NAME]>  
```  
  
## <a name="message-actions-of-functions-and-procedures"></a>関数およびプロシージャのメッセージの動作  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]ストアド プロシージャと関数の操作のため、次のメッセージ アクションを使用します。  
  
|メッセージ|操作|例|  
|-------------|------------|-------------|  
|ストアド プロシージャ要求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT|  
|ストアド プロシージャの応答|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/response|  
|関数の要求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID|  
|関数の応答|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Function/[FN_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETID/response|  
|ストアド プロシージャの要求をパッケージ化|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT|  
|ストアド プロシージャの応答をパッケージ化|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[SP_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/SP_INSERT/response|  
|パッケージ化された関数の要求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID|  
|パッケージ化された関数の応答|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Package/[PACKAGE_NAME]/[FN_NAME]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/CUSTOMER/FN_GETID/response|  
|ストアド プロシージャのオーバー ロードされた要求|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1|  
|ストアド プロシージャの応答をオーバー ロード|http://Microsoft.LobServices.OracleDB/2007/03/[SCHEMA]/Procedure/[SP_NAME]/[OVERLOAD]/response|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_INSERT/overload1/response|  
  
 [スキーマ] コレクションの Oracle の成果物を =たとえば、SCOTT です。  
  
 [SP_NAME] を実行するストアド プロシージャを =たとえば、SP_INSERT です。  
  
 [FN_NAME] 実行する関数を =たとえば、FN_GETID です。  
  
 [PACKAGE_NAME] を対象のプロシージャまたは関数を含むパッケージの名前を = です。  
  
 [オーバー ロード]、オーバー ロードのパラメーターを = です。 使用可能な値は overload1、overload2、およびなどです。  
  
## <a name="see-also"></a>参照  
 [メッセージと BizTalk Adapter 用 Oracle Database のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)