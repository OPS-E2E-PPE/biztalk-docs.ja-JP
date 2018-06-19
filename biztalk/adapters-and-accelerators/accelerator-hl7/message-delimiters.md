---
title: 区切り記号をメッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: 5e25e4fad2eb9e32c87f8a395bd924fc4a1f2eb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960664"
---
# <a name="message-delimiters"></a>メッセージの区切り記号
HL7 標準によって定義されたメッセージのイベントは、次の形式をとります。  
  
-   **フラット ファイル**です。 HL7 2.4 以前のバージョンによって定義されるメッセージのイベントは、フラット ファイルの形式をとります。  
  
-   **XML**です。 HL7 バージョン 2. XML およびバージョン 3 で定義されたメッセージのイベントは、XML ファイルの形式をとります。  
  
 標準 HL7 に位置指定の形式に従っていないために、セグメント、フィールド、コンポーネント、およびフラット ファイルのサブコンポーネント レベルを定義するのに区切り記号を使用します。 次の表には、HL7 フラット ファイルによって使用される既定の区切り記号が一覧表示します。  
  
|区切り記号|値|使用方法|  
|---------------|-----------|-----------|  
|[ セグメント終端記号]|\<cr\>|キャリッジ リターンは、セグメントのレコードを終了します。 この値を変更することはできません。|  
|フィールド区切り文字|&#124;|パイプ文字では、セグメント内で 2 つの連続するデータ フィールドを区切ります。 また、この文字は、各セグメントの最初のデータ フィールドからセグメント ID を区切ります。|  
|[コンポーネントの区切り記号]|^|Hat の文字は、データの横にあるコンポーネントを区切る HL7 標準で許容される範囲でのフィールドです。|  
|サブコンポーネントの区切り記号|&|アンパサンド文字データの横にあるこれらのサブコンポーネントの分離、HL7 標準で許可されている場所のフィールドです。 これらのサブコンポーネントがない場合は、この文字を省略できます。|  
|繰り返し区切り記号|~|チルダ文字は、コンポーネントまたはサブコンポーネント フィールド内の複数の発生を区切る HL7 標準で許可されている場所です。|  
|[エスケープ文字]|\|ST、テキサス州または FT のデータ型に準拠している任意のフィールドまたは ED データ型のデータ (4) コンポーネントでは、エスケープ文字を使用します。 メッセージにエスケープ文字が存在しない場合は、この文字を省略できます。 ただし、メッセージにこれらのサブコンポーネントを使用する場合に含める必要があります。|  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)