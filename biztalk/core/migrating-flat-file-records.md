---
title: フラット ファイル レコードの移行 |Microsoft ドキュメント
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
ms.openlocfilehash: ddd43c231077f4e23efca374edbda5bf152f1415
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710821"
---
# <a name="migrate-flat-file-records"></a><span data-ttu-id="1cfbf-102">フラット ファイル レコードを移行します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-102">Migrate Flat File Records</span></span>

## <a name="overview"></a><span data-ttu-id="1cfbf-103">概要</span><span class="sxs-lookup"><span data-stu-id="1cfbf-103">Overview</span></span>
<span data-ttu-id="1cfbf-104">Microsoft BizTalk Server は、区切り記号の種類を 1 つだけがサポートされています、複数の文字の区切り記号をサポートしています: 子区切り記号。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-104">Microsoft BizTalk Server supports multi-character delimiters, although it supports only one type of delimiter—child delimiter.</span></span> 
  
 <span data-ttu-id="1cfbf-105">次の 3 つのスキーマ注釈は、区切り記号の BizTalk Server で処理を制御: 解析用に 2 つ (**skip_CR**、 **skip_LF**)、もう 1 つのシリアル化用 (**append_newline**)。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-105">Three schema annotations control delimiter handling in BizTalk Server: two for parsing (**skip_CR**, **skip_LF**), and one for serializing (**append_newline**).</span></span> <span data-ttu-id="1cfbf-106">BizTalk Server では、次のようにレコードを移行するときにこれらの注釈を解釈します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-106">BizTalk Server interprets these annotations as follows when migrating records:</span></span>  
  
-   <span data-ttu-id="1cfbf-107">場合、 **skip_CR**注釈の値を持つ**true**と現在の区切り記号がキャリッジ リターン (0x0D)、BizTalk Server はキャリッジ リターンを現在の区切り記号に追加します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-107">If the **skip_CR** annotation has a value of **true** and the current delimiter is not carriage return (0x0D), BizTalk Server adds a carriage return to the current delimiter.</span></span> <span data-ttu-id="1cfbf-108">たとえば、現在の区切り記号がパイプ記号 (0x7C) の場合、パイプ記号の後にキャリッジ リターンが追加されます (0x7C 0x0D)。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-108">For example, if the current delimiter were the pipe symbol (0x7C), the resulting delimiter is a pipe symbol followed by a carriage return (0x7C 0x0D).</span></span> <span data-ttu-id="1cfbf-109">現在の区切り記号がキャリッジ リターンの場合は、これに限り、単一のキャリッジ リターンの値に関係なく **skip_CR**します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-109">If the current delimiter is carriage return, it remains as a single carriage return regardless of the value of **skip_CR**.</span></span>  
  
-   <span data-ttu-id="1cfbf-110">場合、 **skip_LF**注釈の値を持つ**true**、BizTalk Server を追加、ラインフィード文字 (0x0A) 現在の区切り記号をします。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-110">If the **skip_LF** annotation has a value of **true**, BizTalk Server adds a linefeed character (0x0A) to the current delimiter.</span></span> <span data-ttu-id="1cfbf-111">通知することで、上記の例では、現在の区切り記号がパイプ記号 (0x7C) をここでは、次の 3 つの文字の区切り記号になります (0x7C 0x0D 0x0A) 両方 **skip_CR** と **skip_LF** は **true**します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-111">Notice that in the preceding case where the current delimiter is the pipe symbol (0x7C), a three character delimiter results (0x7C 0x0D 0x0A) if both **skip_CR** and **skip_LF** are **true**.</span></span>  
  
-   <span data-ttu-id="1cfbf-112">BizTalk Server の設定は無視されます、 **append_newline**注釈。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-112">BizTalk Server ignores the setting of the **append_newline** annotation.</span></span>  
  
 <span data-ttu-id="1cfbf-113">注釈の概要を理解すると、ほとんどの場合、問題なく移行を行えます。ただし、移行が失敗する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-113">While these interpretations of the annotations ensure the majority of cases migrate without difficulty, there are some cases where migration fails.</span></span> <span data-ttu-id="1cfbf-114">たとえば場合、 **skip_CR**と**skip_LF**が両方とも**true**現在の区切り記号がパイプ記号 (0x7C) して、BizTalk Server では、有効なものとして、次のすべてを受け入れます単一のレコード セット内の区切り記号: 0x7C 0x0D 0x0A、0x7C 0x0D、0x7C 0x0A、および 0x7C します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-114">For example, if **skip_CR** and **skip_LF** are both **true** and the current delimiter is the pipe symbol (0x7C), BizTalk Server accepts all of the following as valid delimiters within a single set of records: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A, and 0x7C.</span></span> <span data-ttu-id="1cfbf-115">区切り記号のようなセットを使用してレコードは、移行できないし、BizTalk Server でのカスタム解析コードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-115">Records using such sets of delimiters cannot be migrated and require custom parser code in BizTalk Server.</span></span>  
  
 <span data-ttu-id="1cfbf-116">BizTalk Server が、区切り記号の 1 つだけの種類がありますは、レコードを簡単に移行できるように、古い注釈を解釈します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-116">Although BizTalk Server has only one type of delimiter, it interprets the old annotations so that records migrate easily.</span></span> <span data-ttu-id="1cfbf-117">BizTalk Server スキーマがの値を持つ場合**def_record_delimdef_field_delim**、 **def_subfield_delim**とでこれらが参照されて**delimiter_type** として**inherit_record**など、BizTalk Server は、対応する値を取得し、ローカルに格納します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-117">If a BizTalk Server schema has values for **def_record_delimdef_field_delim**, **def_subfield_delim**, and these are referenced in **delimiter_type** as **inherit_record**, and so on, BizTalk Server retrieves the corresponding value and stores it locally.</span></span>  
  
 <span data-ttu-id="1cfbf-118">さらに、BizTalk Server は、子を持たないタグ付きの位置指定レコードのフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="1cfbf-118">In addition, BizTalk Server adds fields for tagged positional records without children.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cfbf-119">参照</span><span class="sxs-lookup"><span data-stu-id="1cfbf-119">See Also</span></span>  
 [<span data-ttu-id="1cfbf-120">スキーマの生成と検証に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="1cfbf-120">Known Issues with Schema Generation and Validation</span></span>](../core/known-issues-with-schema-generation-and-validation.md)