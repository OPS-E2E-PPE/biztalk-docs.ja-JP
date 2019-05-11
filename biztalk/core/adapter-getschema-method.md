---
title: アダプターの GetSchema メソッド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c83340c-a775-435c-9633-3a692611e99e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a06e6eedb57ea0cbca1c4572ddf755b9915ca7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361467"
---
# <a name="adapter-getschema-method"></a>アダプターの GetSchema メソッド
参照先の WSDL ファイルは、スキーマ参照のみが含まれていて、埋め込みスキーマが含まれていないとします。 この場合、使用して、 **GetSchema**のメソッド、 **IAdapterConfig**インターフェイス WSDL ファイル内から参照されるスキーマを読み込めません。  
  
 ファイル アダプターのサンプル コードを変更、 **GetSchema** WSDL ファイルに含まれていない外部 XSD ファイルを返すには、AdapterManagement.cs のメソッド。  
  
 次のコードは、 **GetSchema** AdapterManagement.cs ファイルのメソッド。 ここで、Service1.wsdl ファイルには、埋め込みスキーマが含まれているため null 返します。 ない場合は、ケース、XSD スキーマ ファイルに対応する文字列は、返される必要があります。  
  
```  
/// <summary>  
        /// Acquire externally referenced xsd's  
        /// </summary>  
        /// <param name="xsdLocation">Location of schema</param>  
        /// <param name="xsdNamespace">Namespace</param>  
        /// <param name="XSDFileName">Schmea file name (return)</param>  
        /// <returns>Outcome of acquisition</returns>  
        public Result GetSchema(string xsdLocation,  
                                string xsdNamespace,  
                        out string xsdSchema)   
      {  
            xsdSchema = null;  
            return Result.Continue;  
        }  
```