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
# <a name="migrate-flat-file-records"></a><span data-ttu-id="9cc81-102">フラット ファイル レコードを移行します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-102">Migrate Flat File Records</span></span>

## <a name="overview"></a><span data-ttu-id="9cc81-103">概要</span><span class="sxs-lookup"><span data-stu-id="9cc81-103">Overview</span></span>
<span data-ttu-id="9cc81-104">Microsoft BizTalk Server は、区切り記号の種類を 1 つだけがサポートされています、複数の文字の区切り記号をサポートしています: 子区切り記号。</span><span class="sxs-lookup"><span data-stu-id="9cc81-104">Microsoft BizTalk Server supports multi-character delimiters, although it supports only one type of delimiter—child delimiter.</span></span> 
  
 <span data-ttu-id="9cc81-105">次の 3 つのスキーマのコメント区切り記号の BizTalk Server で処理を制御する: 解析するための 2 つ (**skip_CR**、 **skip_LF**)、シリアル化するための 1 つ (**append_newline**)。</span><span class="sxs-lookup"><span data-stu-id="9cc81-105">Three schema annotations control delimiter handling in BizTalk Server: two for parsing (**skip_CR**, **skip_LF**), and one for serializing (**append_newline**).</span></span> <span data-ttu-id="9cc81-106">BizTalk Server では、レコードの移行時に次のようにこれらの注釈を解釈します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-106">BizTalk Server interprets these annotations as follows when migrating records:</span></span>  
  
- <span data-ttu-id="9cc81-107">場合、 **skip_CR**注釈の値を持つ**true**と現在の区切り記号がキャリッジ リターン (0x0D)、BizTalk Server、キャリッジ リターンを現在の区切り記号に追加します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-107">If the **skip_CR** annotation has a value of **true** and the current delimiter is not carriage return (0x0D), BizTalk Server adds a carriage return to the current delimiter.</span></span> <span data-ttu-id="9cc81-108">たとえば、現在の区切り記号がパイプ記号 (0x7C) の場合、パイプ記号の後にキャリッジ リターンが追加されます (0x7C 0x0D)。</span><span class="sxs-lookup"><span data-stu-id="9cc81-108">For example, if the current delimiter were the pipe symbol (0x7C), the resulting delimiter is a pipe symbol followed by a carriage return (0x7C 0x0D).</span></span> <span data-ttu-id="9cc81-109">現在の区切り記号がキャリッジ リターンの場合は、ままである単一のキャリッジ リターンの値に関係なく**skip_CR**します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-109">If the current delimiter is carriage return, it remains as a single carriage return regardless of the value of **skip_CR**.</span></span>  
  
- <span data-ttu-id="9cc81-110">場合、 **skip_LF**注釈の値を持つ**true**改行を追加する BizTalk Server を現在の区切り記号文字 (0x0A)。</span><span class="sxs-lookup"><span data-stu-id="9cc81-110">If the **skip_LF** annotation has a value of **true**, BizTalk Server adds a linefeed character (0x0A) to the current delimiter.</span></span> <span data-ttu-id="9cc81-111">現在の区切り記号がパイプ記号 (0x7C) を前の場合、次の 3 つの文字の区切り記号の結果に注意してください (0x7C 0x0D 0x0A) 両方**skip_CR**と**skip_LF**は**true**.</span><span class="sxs-lookup"><span data-stu-id="9cc81-111">Notice that in the preceding case where the current delimiter is the pipe symbol (0x7C), a three character delimiter results (0x7C 0x0D 0x0A) if both **skip_CR** and **skip_LF** are **true**.</span></span>  
  
- <span data-ttu-id="9cc81-112">BizTalk Server の設定は無視されます、 **append_newline**注釈。</span><span class="sxs-lookup"><span data-stu-id="9cc81-112">BizTalk Server ignores the setting of the **append_newline** annotation.</span></span>  
  
  <span data-ttu-id="9cc81-113">注釈の概要を理解すると、ほとんどの場合、問題なく移行を行えます。ただし、移行が失敗する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9cc81-113">While these interpretations of the annotations ensure the majority of cases migrate without difficulty, there are some cases where migration fails.</span></span> <span data-ttu-id="9cc81-114">たとえば場合、 **skip_CR**と**skip_LF**はどちらも**true**と現在の区切り記号がパイプ記号 (0x7C)、BizTalk Server が有効で、次のすべてを受け入れます単一のレコード セット内の区切り記号: 0x7C 0x0D 0x0A、0x7C 0x0D、0x7C 0x0A、および 0x7C です。</span><span class="sxs-lookup"><span data-stu-id="9cc81-114">For example, if **skip_CR** and **skip_LF** are both **true** and the current delimiter is the pipe symbol (0x7C), BizTalk Server accepts all of the following as valid delimiters within a single set of records: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A, and 0x7C.</span></span> <span data-ttu-id="9cc81-115">このような区切り記号を使用レコードは、移行できないし、BizTalk Server でのカスタム解析コードが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cc81-115">Records using such sets of delimiters cannot be migrated and require custom parser code in BizTalk Server.</span></span>  
  
  <span data-ttu-id="9cc81-116">BizTalk Server には、区切り記号の種類を 1 つだけは、レコードを簡単に移行するため、古い注釈を解釈します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-116">Although BizTalk Server has only one type of delimiter, it interprets the old annotations so that records migrate easily.</span></span> <span data-ttu-id="9cc81-117">BizTalk Server スキーマの値がある場合**def_record_delimdef_field_delim**、 **def_subfield_delim**で参照されているこれら**delimiter_type** として**inherit_record**で BizTalk Server が対応する値を取得し、ローカルに格納します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-117">If a BizTalk Server schema has values for **def_record_delimdef_field_delim**, **def_subfield_delim**, and these are referenced in **delimiter_type** as **inherit_record**, and so on, BizTalk Server retrieves the corresponding value and stores it locally.</span></span>  
  
  <span data-ttu-id="9cc81-118">さらに、BizTalk Server では、子を持たないタグ付きの位置指定レコードのフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cc81-118">In addition, BizTalk Server adds fields for tagged positional records without children.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc81-119">参照</span><span class="sxs-lookup"><span data-stu-id="9cc81-119">See Also</span></span>  
 [<span data-ttu-id="9cc81-120">スキーマの生成と検証に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="9cc81-120">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)