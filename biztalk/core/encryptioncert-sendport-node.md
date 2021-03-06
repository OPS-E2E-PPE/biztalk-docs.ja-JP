---
title: EncryptionCert (SendPort ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EncryptionCert node [binding file]
ms.assetid: 83dff67e-1b3c-4c3d-91a2-d826a498635f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a314490ecb9b92babab690e892ee7ce11ebfdec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349494"
---
# <a name="encryptioncert-sendport-node"></a>EncryptionCert (SendPort ノード)
バインド ファイルの SendPort ノードの EncryptionCert ノードには、バインド ファイルと共にエクスポートされる送信ポートで使用される暗号化証明書に関する情報が含まれています。  
  
## <a name="nodes-in-the-encryptioncert-node"></a>EncryptionCert ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|LongName|属性|xs:string|証明書の長い名前を指定します。|任意|既定値: 空|  
|ShortName|属性|xs:string|証明書の短い名前を指定します。|任意|既定値: 空|  
|UsageType|属性|CertUsageType (SimpleType)|この証明書の使用目的を指定します|必須|既定値: なし<br /><br /> 使用可能な値で使用できる、 [Microsoft.BizTalk.ExplorerOM.CertUsageType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.certusagetype.aspx)列挙体。|  
|拇印|属性|xs:string|拇印または証明書の一意の ID を指定します。|任意|既定値: 空|