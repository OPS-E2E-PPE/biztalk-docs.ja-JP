---
title: フラット ファイル レコードの移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f055b6a572e357a520b9679796ad0288dda19f3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994075"
---
# <a name="migrate-flat-file-records"></a>フラット ファイル レコードを移行します。

## <a name="overview"></a>概要
Microsoft BizTalk Server は、区切り記号の種類を 1 つだけがサポートされています、複数の文字の区切り記号をサポートしています: 子区切り記号。 
  
 次の 3 つのスキーマのコメント区切り記号の BizTalk Server で処理を制御する: 解析するための 2 つ (**skip_CR**、 **skip_LF**)、シリアル化するための 1 つ (**append_newline**)。 BizTalk Server では、レコードの移行時に次のようにこれらの注釈を解釈します。  
  
- 場合、 **skip_CR**注釈の値を持つ**true**と現在の区切り記号がキャリッジ リターン (0x0D)、BizTalk Server、キャリッジ リターンを現在の区切り記号に追加します。 たとえば、現在の区切り記号がパイプ記号 (0x7C) の場合、パイプ記号の後にキャリッジ リターンが追加されます (0x7C 0x0D)。 現在の区切り記号がキャリッジ リターンの場合は、ままである単一のキャリッジ リターンの値に関係なく**skip_CR**します。  
  
- 場合、 **skip_LF**注釈の値を持つ**true**改行を追加する BizTalk Server を現在の区切り記号文字 (0x0A)。 現在の区切り記号がパイプ記号 (0x7C) を前の場合、次の 3 つの文字の区切り記号の結果に注意してください (0x7C 0x0D 0x0A) 両方**skip_CR**と**skip_LF**は**true**.  
  
- BizTalk Server の設定は無視されます、 **append_newline**注釈。  
  
  注釈の概要を理解すると、ほとんどの場合、問題なく移行を行えます。ただし、移行が失敗する場合もあります。 たとえば場合、 **skip_CR**と**skip_LF**はどちらも**true**と現在の区切り記号がパイプ記号 (0x7C)、BizTalk Server が有効で、次のすべてを受け入れます単一のレコード セット内の区切り記号: 0x7C 0x0D 0x0A、0x7C 0x0D、0x7C 0x0A、および 0x7C です。 このような区切り記号を使用レコードは、移行できないし、BizTalk Server でのカスタム解析コードが必要です。  
  
  BizTalk Server には、区切り記号の種類を 1 つだけは、レコードを簡単に移行するため、古い注釈を解釈します。 BizTalk Server スキーマの値がある場合**def_record_delimdef_field_delim**、 **def_subfield_delim**で参照されているこれら**delimiter_type** として**inherit_record**で BizTalk Server が対応する値を取得し、ローカルに格納します。  
  
  さらに、BizTalk Server では、子を持たないタグ付きの位置指定レコードのフィールドを追加します。  
  
## <a name="see-also"></a>参照  
 [スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)