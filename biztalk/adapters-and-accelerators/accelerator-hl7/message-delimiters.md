---
title: メッセージの区切り記号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, events
- messages, XML messages
- events
- delimiters
- messages, delimiters
- flat files
- XML messages
- messages, flat files
ms.assetid: d25bf6db-5512-4c82-be0e-00da024c55d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3339ded8edf46f7c5b96317cdf7a3ec822ec808b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001499"
---
# <a name="message-delimiters"></a>メッセージの区切り記号
HL7 標準によって定義されたメッセージのイベントは、次の形式をとります。  
  
- **フラット ファイル**します。 HL7 2.4 以前のバージョンによって定義されたメッセージのイベントは、フラット ファイルの形式になります。  
  
- **XML**します。 HL7 バージョン 2. XML およびバージョン 3 で定義されたメッセージのイベントは、XML ファイルの形式になります。  
  
  標準 HL7 が位置指定の形式に従っていないために、セグメント、フィールド、コンポーネント、およびフラット ファイルのサブコンポーネントの情報のレベルを定義するのに区切り記号を使用します。 HL7 のフラット ファイルによって使用される既定の区切り記号を次の表に示します。  
  
|区切り記号|値|使用方法|  
|---------------|-----------|-----------|  
|[ セグメント終端記号]|\<cr\>|キャリッジ リターンとは、セグメントのレコードを終了します。 この値を変更することはできません。|  
|フィールドの区切り記号|&#124;|パイプ文字では、セグメント内で 2 つの連続するデータ フィールドを区切ります。 この文字は、各セグメントには、最初のデータ フィールドからセグメント ID も分離します。|  
|[コンポーネントの区切り記号]|^|Hat の文字データの横にあるコンポーネントの分離、HL7 標準で許可されている場所のフィールドします。|  
|サブコンポーネントの区切り記号|&|アンパサンド文字は、データの隣接するサブコンポーネントを区切る HL7 標準で許可されている場所のフィールドします。 サブコンポーネントがない場合は、この文字を省略できます。|  
|繰り返し区切り記号|~|チルダ文字は、コンポーネントまたはサブコンポーネント フィールド内の複数の発生を区切る HL7 標準で許可します。|  
|[エスケープ文字]|\|ST、テキサス州または FT のデータ型に準拠している任意のフィールドと ED データ型のデータ (4 番目) のコンポーネントは、エスケープ文字を使用します。 メッセージにエスケープ文字が存在しない場合は、この文字を省略できます。 ただし、メッセージのサブコンポーネントを使用する場合に追加する必要があります。|  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)