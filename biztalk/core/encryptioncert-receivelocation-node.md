---
title: EncryptionCert (ReceiveLocation ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 04dc4021-8cd9-45e7-8339-8f22e29f4be6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec4d0ff769c7a8ca297800f427c4ebbae48a8640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="encryptioncert-receivelocation-node"></a>EncryptionCert (ReceiveLocation ノード)
バインド ファイルの ReceiveLocation ノードの EncryptionCert ノードには、そのバインド ファイルと共にエクスポートされる受信場所で使用される暗号化証明書に関する情報が格納されます。  
  
## <a name="nodes-in-the-encryptioncert-node"></a>EncryptionCert ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|LongName|属性|xs:string|証明書の長い名前を指定します。|任意|既定値: 空|  
|ShortName|属性|xs:string|証明書の短い名前を指定します。|任意|既定値: 空|  
|UsageType|属性|CertUsageType (SimpleType)|この証明書の用途を指定します。|必須|既定値: なし<br /><br /> 使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)列挙します。|  
|ThumbPrint|属性|xs:string|証明書の拇印または一意の ID を指定します。|任意|既定値: 空|