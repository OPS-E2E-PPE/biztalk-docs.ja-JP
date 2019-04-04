---
title: クロス フィールド検証の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f0c6ae8-0b8a-4826-9dfb-bf27e5ff7fa6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97951adc5c98f8350e7f42c92214f89558f2a70d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014491"
---
# <a name="configuring-cross-field-validation"></a><span data-ttu-id="42166-102">クロスフィールド検証の構成</span><span class="sxs-lookup"><span data-stu-id="42166-102">Configuring Cross-Field Validation</span></span>
<span data-ttu-id="42166-103">このトピックでは、EDI でエンコードされたメッセージのトランザクション セット データ要素に対するクロスフィールド/セグメント検証を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42166-103">This topic describes how to enable cross field/segment validation on transaction-set data elements in EDI-encoded messages.</span></span> <span data-ttu-id="42166-104">これを行うには、2 つの設定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="42166-104">To do so, you need to make two settings:</span></span>  
  
-   <span data-ttu-id="42166-105">EDI スキーマの注釈にクロスフィールド検証フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="42166-105">Set the cross-field validation flag in an annotation of the EDI schema.</span></span> <span data-ttu-id="42166-106">X12 または HIPAA スキーマでは、これは、 **X12ConditionDesignator_Check**フラグ。</span><span class="sxs-lookup"><span data-stu-id="42166-106">For X12 or HIPAA schemas, this is the **X12ConditionDesignator_Check** flag.</span></span> <span data-ttu-id="42166-107">EDIFACT スキーマの場合、これは、 **EdifactDependencyRule_Check**フラグ。</span><span class="sxs-lookup"><span data-stu-id="42166-107">For EDIFACT schemas, this is the **EdifactDependencyRule_Check** flag.</span></span>  
  
-   <span data-ttu-id="42166-108">アグリーメントのプロパティで EDI 型の検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="42166-108">Enable EDI-type validation in the agreement properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42166-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="42166-109">Prerequisites</span></span>  
 <span data-ttu-id="42166-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="42166-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="configuring-cross-field-validation"></a><span data-ttu-id="42166-111">クロスフィールド検証の構成</span><span class="sxs-lookup"><span data-stu-id="42166-111">Configuring Cross-Field Validation</span></span>  
  
1. <span data-ttu-id="42166-112">BizTalk エディターでスキーマを開きます。</span><span class="sxs-lookup"><span data-stu-id="42166-112">Open your schema in BizTalk Editor.</span></span>  
  
2. <span data-ttu-id="42166-113">X12 または HIPAA スキーマ、検索、 **X12ConditionDesignator_Check**スキーマの appinfo セクションの注釈のフラグ。</span><span class="sxs-lookup"><span data-stu-id="42166-113">For an X12 or HIPAA schema, find the **X12ConditionDesignator_Check** flag in an annotation in the appinfo section of the schema.</span></span> <span data-ttu-id="42166-114">設定**はい**します。</span><span class="sxs-lookup"><span data-stu-id="42166-114">Set it to **Yes**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="42166-115">X12ConditionDesignator_Check フラグを設定して**はい**BizTalk スキーマ エディターから実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="42166-115">Setting the flag X12ConditionDesignator_Check to **Yes** cannot be performed from BizTalk Schema Editor.</span></span> <span data-ttu-id="42166-116">フラグを設定するには、メモ帳などのテキスト エディターで開いて編集し、スキーマ ファイル (.xsd) を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42166-116">For setting the flag, you will have to open it in a notepad or similar text editor, edit, and then save the schema file (.xsd).</span></span>  
  
3. <span data-ttu-id="42166-117">EDIFACT スキーマで、検索、 **EdifactDependencyRule_Check**スキーマの appinfo セクションの注釈のフラグ。</span><span class="sxs-lookup"><span data-stu-id="42166-117">For an EDIFACT schema, find the **EdifactDependencyRule_Check** flag in the annotation in the appinfo section of the schema.</span></span> <span data-ttu-id="42166-118">設定**はい**します。</span><span class="sxs-lookup"><span data-stu-id="42166-118">Set it to **Yes**.</span></span>  
  
4. <span data-ttu-id="42166-119">スキーマの適切なセグメントに対して、適用する関係条件 (X12 および HIPAA) または依存ルール (EDIFACT) を指定します。</span><span class="sxs-lookup"><span data-stu-id="42166-119">For the applicable segments of the schema, specify the relational conditions (X12 and HIPAA) or dependency rules (EDIFACT) that apply.</span></span> <span data-ttu-id="42166-120">詳細については、[クロス フィールド/セグメント検証](../core/cross-field-segment-validation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42166-120">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="42166-121">クロスフィールド検証の条件またはルールは、EDI スキーマのセグメントに対して入力されます。</span><span class="sxs-lookup"><span data-stu-id="42166-121">A cross-field validation condition or rule is entered for a segment in an EDI schema.</span></span> <span data-ttu-id="42166-122">セグメントではなくデータ要素に対してクロスフィールド検証ルールを入力すると、スキーマ検証の実行時に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="42166-122">If you enter a cross-field validation rule for a data element, rather than a segment, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will generate a warning when schema validation is performed.</span></span>  
  
5. <span data-ttu-id="42166-123">**検証**ページ (で、**トランザクション セットの設定**セクション) の一方向アグリーメント タブの**アグリーメントのプロパティ**関連するアグリーメントは、ダイアログ ボックス必ず、 **EDI の種類の検証**プロパティが選択されています。</span><span class="sxs-lookup"><span data-stu-id="42166-123">In the **Validation** page (under the **Transaction Set Settings** section) of the one-way agreement tab of the **Agreement Properties** dialog box for relevant agreement, make sure that the **EDI type Validation** property is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42166-124">参照</span><span class="sxs-lookup"><span data-stu-id="42166-124">See Also</span></span>  
 [<span data-ttu-id="42166-125">EDI スキーマの開発</span><span class="sxs-lookup"><span data-stu-id="42166-125">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)