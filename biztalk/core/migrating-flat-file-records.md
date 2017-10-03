---
title: "フラット ファイル レコードの移行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28daa8426dff3d9cbe9330430e4ba3de64410e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="migrating-flat-file-records"></a>フラット ファイル レコードの移行
Microsoft [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] および Microsoft [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] では、解析中およびシリアル化中のフラット ファイル レコードでサポートされる区切り記号は、1 文字の区切り記号です。 この制限は、区切り記号の処理をより柔軟で相殺されます。 [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]および[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]レコード、フィールド、およびサブフィールドに異なる区切り記号の設定もサポートします。 これに対して、Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、複数の文字による区切り記号をサポートしています。ただし、サポート対象となる区切り記号は、子区切り記号のみです。 区切り記号の処理が向上したため、[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] では、[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] や [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] のフラット ファイル レコードを処理する方法に影響が出る場合があります。  
  
 次の 3 つのスキーマ注釈での処理の区切り記号の制御[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]、解析用に 2 つ (**skip_CR**、 **skip_LF**)、もう 1 つのシリアル化用 (**append_newline**). [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]次のようにレコードを移行するときにこれらの注釈を解釈します。  
  
-   場合、 **skip_CR**注釈の値を持つ**true**現在の区切り記号がキャリッジ リターン (0x0D)、および[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]はキャリッジ リターンを現在の区切り記号に追加します。 たとえば、現在の区切り記号がパイプ記号 (0x7C) の場合、パイプ記号の後にキャリッジ リターンが追加されます (0x7C 0x0D)。 現在の区切り記号がキャリッジ リターンの場合は、そのに限り、単一のキャリッジ リターンの値に関係なく**skip_CR**です。  
  
-   場合、 **skip_LF**注釈の値を持つ**true**、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]改行を追加文字 (0x0A) を現在の区切り記号。 で現在の区切り記号がパイプ記号 (0x7C) を前者の場合、次の 3 つの文字の区切り記号は結果に注意してください (0x7C 0x0D 0x0A) 場合は、両方**skip_CR**と**skip_LF**は**true**.  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]設定は無視されます、 **append_newline**注釈。  
  
 注釈の概要を理解すると、ほとんどの場合、問題なく移行を行えます。ただし、移行が失敗する場合もあります。 たとえば場合、 **skip_CR**と**skip_LF**が両方とも**true**し、現在の区切り記号がパイプ記号 (0x7C)[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]すべての同意、次のレコードの 1 つのセット内で有効な区切り記号として: 0x7C 0x0D 0x0A、0x7C 0x0D、0x7C 0x0A、および 0x7C します。 ただし、このような区切り記号を使用するレコードは移行できないので、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ではカスタム解析コードが必要になります。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では 1 種類の区切り記号にしか対応していませんが、古い注釈を解釈して、レコードを簡単に移行できます。 場合、[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]または[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]スキーマの値を持つ**def_record_delimdef_field_delim**、 **def_subfield_delim**とでこれらが参照されて**delimiter_type**として**inherit_record**など、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]対応する値を取得し、ローカルに格納します。  
  
 さらに、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] では、子を持たないタグ付きの位置指定レコードのフィールドを追加します。  
  
## <a name="see-also"></a>参照  
 [スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)