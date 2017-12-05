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
ms.openlocfilehash: c719a1be93458de456cb528c415e18e7a193bf71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="migrating-flat-file-records"></a>フラット ファイル レコードの移行
Microsoft [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] および Microsoft [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] では、解析中およびシリアル化中のフラット ファイル レコードでサポートされる区切り記号は、1 文字の区切り記号です。 この制限は、区切り記号の処理をより柔軟で相殺されます。 [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]および[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]レコード、フィールド、およびサブフィールドに異なる区切り記号の設定もサポートします。 これに対し、Microsoft BizTalk Server をサポートしている複数の文字の区切り記号を区切り記号の種類を 1 つだけがサポートされています: 子区切り記号。 区切り記号の処理の機能強化が変わる可能性がありますか[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]フラット ファイル レコードは、BizTalk Server で処理されます。  
  
 次の 3 つのスキーマ注釈での処理の区切り記号の制御[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]、解析用に 2 つ (**skip_CR**、 **skip_LF**)、もう 1 つのシリアル化用 (**append_newline**). BizTalk Server では、次のようにレコードを移行するときにこれらの注釈を解釈します。  
  
-   場合、 **skip_CR**注釈の値を持つ**true**と現在の区切り記号がキャリッジ リターン (0x0D)、BizTalk Server はキャリッジ リターンを現在の区切り記号に追加します。 たとえば、現在の区切り記号がパイプ記号 (0x7C) の場合、パイプ記号の後にキャリッジ リターンが追加されます (0x7C 0x0D)。 現在の区切り記号がキャリッジ リターンの場合は、そのに限り、単一のキャリッジ リターンの値に関係なく**skip_CR**です。  
  
-   場合、 **skip_LF**注釈の値を持つ**true**、BizTalk Server を追加、ラインフィード文字 (0x0A) 現在の区切り記号をします。 で現在の区切り記号がパイプ記号 (0x7C) を前者の場合、次の 3 つの文字の区切り記号は結果に注意してください (0x7C 0x0D 0x0A) 場合は、両方**skip_CR**と**skip_LF**は**true**.  
  
-   BizTalk Server の設定は無視されます、 **append_newline**注釈。  
  
 注釈の概要を理解すると、ほとんどの場合、問題なく移行を行えます。ただし、移行が失敗する場合もあります。 たとえば場合、 **skip_CR**と**skip_LF**が両方とも**true**し、現在の区切り記号がパイプ記号 (0x7C)[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]と[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]すべての同意、次のレコードの 1 つのセット内で有効な区切り記号として: 0x7C 0x0D 0x0A、0x7C 0x0D、0x7C 0x0A、および 0x7C します。 区切り記号のようなセットを使用してレコードは、移行できないし、BizTalk Server でのカスタム解析コードが必要です。  
  
 BizTalk Server が、区切り記号の 1 つだけの種類がありますは、レコードを簡単に移行できるように、古い注釈を解釈します。 場合、[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]または[!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)]スキーマの値を持つ**def_record_delimdef_field_delim**、 **def_subfield_delim**とでこれらが参照されて**delimiter_type**として**inherit_record**など、BizTalk Server は、対応する値を取得し、ローカルに格納します。  
  
 さらに、BizTalk Server は、子を持たないタグ付きの位置指定レコードのフィールドを追加します。  
  
## <a name="see-also"></a>参照  
 [スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)