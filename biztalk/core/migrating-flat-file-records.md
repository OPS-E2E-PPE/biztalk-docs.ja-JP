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
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd43c231077f4e23efca374edbda5bf152f1415
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="migrate-flat-file-records"></a>フラット ファイル レコードを移行します。

## <a name="overview"></a>概要
Microsoft BizTalk Server は、区切り記号の種類を 1 つだけがサポートされています、複数の文字の区切り記号をサポートしています: 子区切り記号。 
  
 次の 3 つのスキーマ注釈は、区切り記号の BizTalk Server で処理を制御: 解析用に 2 つ (**skip_CR**、 **skip_LF**)、もう 1 つのシリアル化用 (**append_newline**)。 BizTalk Server では、次のようにレコードを移行するときにこれらの注釈を解釈します。  
  
-   場合、 **skip_CR**注釈の値を持つ**true**と現在の区切り記号がキャリッジ リターン (0x0D)、BizTalk Server はキャリッジ リターンを現在の区切り記号に追加します。 たとえば、現在の区切り記号がパイプ記号 (0x7C) の場合、パイプ記号の後にキャリッジ リターンが追加されます (0x7C 0x0D)。 現在の区切り記号がキャリッジ リターンの場合は、これに限り、単一のキャリッジ リターンの値に関係なく **skip_CR**します。  
  
-   場合、 **skip_LF**注釈の値を持つ**true**、BizTalk Server を追加、ラインフィード文字 (0x0A) 現在の区切り記号をします。 通知することで、上記の例では、現在の区切り記号がパイプ記号 (0x7C) をここでは、次の 3 つの文字の区切り記号になります (0x7C 0x0D 0x0A) 両方 **skip_CR** と **skip_LF** は **true**します。  
  
-   BizTalk Server の設定は無視されます、 **append_newline**注釈。  
  
 注釈の概要を理解すると、ほとんどの場合、問題なく移行を行えます。ただし、移行が失敗する場合もあります。 たとえば場合、 **skip_CR**と**skip_LF**が両方とも**true**現在の区切り記号がパイプ記号 (0x7C) して、BizTalk Server では、有効なものとして、次のすべてを受け入れます単一のレコード セット内の区切り記号: 0x7C 0x0D 0x0A、0x7C 0x0D、0x7C 0x0A、および 0x7C します。 区切り記号のようなセットを使用してレコードは、移行できないし、BizTalk Server でのカスタム解析コードが必要です。  
  
 BizTalk Server が、区切り記号の 1 つだけの種類がありますは、レコードを簡単に移行できるように、古い注釈を解釈します。 BizTalk Server スキーマがの値を持つ場合**def_record_delimdef_field_delim**、 **def_subfield_delim**とでこれらが参照されて**delimiter_type** として**inherit_record**など、BizTalk Server は、対応する値を取得し、ローカルに格納します。  
  
 さらに、BizTalk Server は、子を持たないタグ付きの位置指定レコードのフィールドを追加します。  
  
## <a name="see-also"></a>参照  
 [スキーマの生成と検証に関する既知の問題](../core/known-issues-with-schema-generation-and-validation.md)