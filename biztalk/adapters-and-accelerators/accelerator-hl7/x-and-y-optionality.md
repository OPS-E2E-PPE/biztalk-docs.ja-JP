---
title: '&#39;X&#39;と&#39;Y&#39; Optionality |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, Y optionality
- segments, SegmentDataElements table
- SegmentDataElements table
- segments, X optionality
ms.assetid: 8a59b407-95a2-45ba-a8d6-db4154c91d7b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320e0188a0987601daf65c011cc24aabc49b14cb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2018
---
# <a name="39x39-and-39y39-optionality"></a>&#39;X&#39;と&#39;Y&#39; Optionality
HL7 Access データベースに SegmentDataElements テーブルにはとして設定されているいくつかのデータ項目 (フィールド) が含まれています**要求数/Opt = X**のように、HL7 標準はこのフィールドに関連付けませんこのトリガー イベントを意味します次の表にします。  
  
|Segment|バージョン|章|データ項目|必要な/<br /><br /> 省略可|レポート|数値|HTML 標準|  
|-------------|-------------|-------------|---------------|-----------------------------|------------|------------|-------------------|  
|OBX|2.4|7.4.2.9|00577|×|Y|5|ch07.htm#Heading113|  
|OBX|2.4|7.4.2.8|00576|×||0|ch07.htm#Heading112|  
|OBX|2.4|7.4.2.6|00574|×||0|ch07.htm#Heading107|  
|OBX|2.4|7.4.2.17|00936|×|Y|0|ch07.htm#Heading121|  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]トリガー イベントで指定されていないどのような必須/オプションのルールを決定するかの選択肢があります。 ローカル サイトの条件に基づき、optionality ルールを適用する決定可能性があります。 既定では、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]として示されている 23 フィールドは、省略可能なフィールドとして"X"です。  
  
> [!NOTE]
>  値"Y"はエラーのために、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Access データベース。 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] 想定されるすべての値**Y**と**空白**は省略可能です。  
  
## <a name="see-also"></a>参照  
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)