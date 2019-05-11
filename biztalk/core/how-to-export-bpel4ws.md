---
title: BPEL4WS にエクスポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 655c3947283b5cd4cb45d863c416051d08a37a98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385057"
---
# <a name="how-to-export-bpel4ws"></a><span data-ttu-id="bbe8e-102">BPEL4WS にエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="bbe8e-102">How to Export BPEL4WS</span></span>
<span data-ttu-id="bbe8e-103">既存の BizTalk オーケストレーションを BPEL4WS にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-103">You can export an existing BizTalk orchestration to BPEL4WS.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bbe8e-104">このリリースの BizTalk Server では、BPEL4WS 1.1 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="bbe8e-105">BPEL4WS 1.0 をインポートまたはエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="bbe8e-106">エクスポートする場合コンパイル BPEL4WS 準拠では、オーケストレーションには、xlang/s と BPEL4WS、間に共通の機能または動作に影響を与えることがなく BPEL4WS に変換できる機能のみが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-106">If you are exporting, BPEL4WS compliance for compilation requires that orchestrations contain only features that are common between XLANG/s and BPEL4WS, or features that can be translated into BPEL4WS without affecting behavior.</span></span>  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a><span data-ttu-id="bbe8e-107">BPEL4WS 準拠するためのオーケストレーションの制限をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-107">Export restrictions on orchestrations for BPEL4WS compliance</span></span>  
  
-   <span data-ttu-id="bbe8e-108">オーケストレーションの呼び出し図形またはオーケストレーションの開始図形を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-108">You cannot use the Call Orchestration shape or the Start Orchestration shape.</span></span>  
  
-   <span data-ttu-id="bbe8e-109">変換図形を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-109">You cannot use the Transform shape.</span></span>  
  
-   <span data-ttu-id="bbe8e-110">カスタム .NET コンポーネントのメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-110">You cannot invoke methods on custom .NET components.</span></span>  
  
-   <span data-ttu-id="bbe8e-111">実行時間の長いトランザクションにタイムアウトを適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-111">You cannot apply a timeout to a long-running transaction.</span></span>  
  
-   <span data-ttu-id="bbe8e-112">オーケストレーションでは、パラメーターを受け取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-112">Your orchestration cannot take parameters.</span></span>  
  
-   <span data-ttu-id="bbe8e-113">呼び出し可能な補正ハンドラーは、パラメーターを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-113">Callable compensation handlers cannot have parameters.</span></span>  
  
-   <span data-ttu-id="bbe8e-114">変数の型は、XPATH でサポート可能なである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-114">Variable types must be supportable in XPATH.</span></span>  
  
-   <span data-ttu-id="bbe8e-115">中断図形を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-115">You cannot use the Suspend shape.</span></span>  
  
-   <span data-ttu-id="bbe8e-116">リテラル値には、次の種類のいずれかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-116">Literal values must be one of the following types:</span></span>  
  
     <span data-ttu-id="bbe8e-117">boolean、char、byte、sbyte、int32、uint32、int64、uint64、single、double、文字列</span><span class="sxs-lookup"><span data-stu-id="bbe8e-117">boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double, string</span></span>  
  
-   <span data-ttu-id="bbe8e-118">算術演算子は、次の数値型のオペランドに対してのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-118">Arithmetic operators are allowed only on operands of following numeric types:</span></span>  
  
     <span data-ttu-id="bbe8e-119">byte、sbyte、int32、uint32、int64、uint64、single、double</span><span class="sxs-lookup"><span data-stu-id="bbe8e-119">byte, sbyte, int32, uint32, int64, uint64, single, double</span></span>  
  
-   <span data-ttu-id="bbe8e-120">関係演算子は、char 型に適用できません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-120">Relational operators cannot be applied to type char.</span></span>  
  
-   <span data-ttu-id="bbe8e-121">式では servicelink プロパティへの参照を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-121">You cannot make a reference to a servicelink property in an expression.</span></span>  
  
-   <span data-ttu-id="bbe8e-122">間で任意の操作を実行することはできません、**送信**図形と**受信**同じ要求-応答の送信ポートを使用する図形。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-122">You cannot perform any actions between a **Send** shape and a **Receive** shape that use the same outbound request-response port.</span></span>  
  
-   <span data-ttu-id="bbe8e-123">参照を格納している別のプロジェクトに参照を使用して、web サービスでは、間接的に参照できません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-123">You cannot indirectly reference a web service, as through a reference to another project that contains a reference.</span></span> <span data-ttu-id="bbe8e-124">プロジェクトで web サービスを明示的に参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-124">You must explicitly reference the web service in your project.</span></span>  
  
-   <span data-ttu-id="bbe8e-125">遅延定数 DateTime や TimeSpan を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-125">You cannot specify a constant DateTime or TimeSpan in a delay.</span></span> <span data-ttu-id="bbe8e-126">代わりに、System.Xml 名前空間では、変換クラスのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-126">Instead, use one of the conversion classes in the System.Xml namespace:</span></span>  
  
     <span data-ttu-id="bbe8e-127">定数 datetime の場合。System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="bbe8e-127">For a constant DateTime: System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span></span>  
  
     <span data-ttu-id="bbe8e-128">定数 timespan の場合。System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span><span class="sxs-lookup"><span data-stu-id="bbe8e-128">For a constant TimeSpan: System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbe8e-129">文字リテラルは、符号なし整数としてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-129">Character literals are exported as unsigned integers.</span></span> <span data-ttu-id="bbe8e-130">たとえば、97 としてエクスポートされます。 'a'、'b' は 98、およびなどとしてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-130">For example, 'a' is exported as 97, 'b' is exported as 98, and so forth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bbe8e-131">識別子名は、W3C Extensible Markup Language (XML) 1.0 仕様に準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-131">Identifier names must conform to the W3C Extensible Markup Language (XML) 1.0 specification.</span></span>  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a><span data-ttu-id="bbe8e-132">オーケストレーションを BPEL4WS にエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="bbe8e-132">To export an orchestration to BPEL4WS</span></span>  
  
1.  <span data-ttu-id="bbe8e-133">BizTalk オーケストレーションの種類の新しい項目をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-133">Add a new item of type BizTalk Orchestration to your project.</span></span>  
  
2.  <span data-ttu-id="bbe8e-134">オーケストレーションのプロパティ ウィンドウを表示し、デザイン画面をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-134">Click the design surface to bring up the Orchestration Properties window.</span></span>  
  
3.  <span data-ttu-id="bbe8e-135">設定**エクスポート可能なモジュール**を True にします。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-135">Set **Module Exportable** to True.</span></span>  
  
4.  <span data-ttu-id="bbe8e-136">型の名前空間で**モジュール XML ターゲットの Namespace**します。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-136">Type in the namespace you want for **Module XML Target Namespace**.</span></span>  
  
5.  <span data-ttu-id="bbe8e-137">設定**エクスポート可能なオーケストレーション**を True にします。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-137">Set **Orchestration Exportable** to True.</span></span>  
  
6.  <span data-ttu-id="bbe8e-138">型の名前空間で**オーケストレーションの XML ターゲットの Namespace**します。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-138">Type in the namespace you want for **Orchestration XML Target Namespace**.</span></span>  
  
7.  <span data-ttu-id="bbe8e-139">ソリューション エクスプ ローラーで右クリックします。オーケストレーションの ODX ファイルです。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-139">In Solution Explorer, right-click the .ODX file for your orchestration.</span></span>  
  
8.  <span data-ttu-id="bbe8e-140">選択**BPEL にエクスポート**します。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-140">Select **Export to BPEL**.</span></span>  
  
     <span data-ttu-id="bbe8e-141">オーケストレーションが BPEL4WS にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-141">Your orchestration will be exported to BPEL4WS.</span></span> <span data-ttu-id="bbe8e-142">成功を確認または問題を診断するには、出力ウィンドウとタスクの一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-142">See the Output Window and Task List to confirm success or diagnose problems.</span></span> <span data-ttu-id="bbe8e-143">エクスポートが完了すると、します。WSDL ファイルとします。BPEL ファイルがプロジェクト ディレクトリに作成されます。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-143">Once your export succeeds, a .WSDL file and a .BPEL file will be created in your project directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbe8e-144">ロール リンク (リンク) への代入または動的なポートへのリテラル割り当てが、オーケストレーションが含まれる場合、BizTalk は、ダミーの BPEL4WS エンドポイント参照を生成し、警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="bbe8e-144">If your orchestration contains an assignment to a role link (service link) or a literal assignment to a dynamic port, BizTalk generates a dummy BPEL4WS endpoint reference and raises a warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe8e-145">参照</span><span class="sxs-lookup"><span data-stu-id="bbe8e-145">See Also</span></span>  
 <span data-ttu-id="bbe8e-146">[BPEL4WS をインポートする方法](../core/how-to-import-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="bbe8e-146">[How to Import BPEL4WS](../core/how-to-import-bpel4ws.md) </span></span>  
 [<span data-ttu-id="bbe8e-147">XLANG-s から BPEL4WS への種類の変換</span><span class="sxs-lookup"><span data-stu-id="bbe8e-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)