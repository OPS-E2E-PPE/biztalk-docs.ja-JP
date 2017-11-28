---
title: "BPEL4WS にエクスポートする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BPEL4WS, exporting
- BPEL4WS, restrictions
- orchestrations, BPEL4WS
ms.assetid: 4648dfcf-cf48-4471-b088-07252c080fb8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16c2e34b498a9fb8d5fd3f6e69f022c2876a763
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-bpel4ws"></a><span data-ttu-id="1b8cf-102">BPEL4WS にエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="1b8cf-102">How to Export BPEL4WS</span></span>
<span data-ttu-id="1b8cf-103">既存の BizTalk オーケストレーションを BPEL4WS にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-103">You can export an existing BizTalk orchestration to BPEL4WS.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1b8cf-104">BizTalk Server のこのリリースでは、BPEL4WS 1.1 をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-104">This release of BizTalk Server supports BPEL4WS 1.1.</span></span> <span data-ttu-id="1b8cf-105">BPEL4WS 1.0 をインポートまたはエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-105">You cannot import or export BPEL4WS 1.0.</span></span>  
  
 <span data-ttu-id="1b8cf-106">オーケストレーションをエクスポートする場合、コンパイルにおける BPEL4WS 準拠の関係上、そのオーケストレーションには、XLANG/s と BPEL4WS 間で共通の機能だけ、または、動作に影響することなく BPEL4WS に変換することのできる機能だけが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-106">If you are exporting, BPEL4WS compliance for compilation requires that orchestrations contain only features that are common between XLANG/s and BPEL4WS, or features that can be translated into BPEL4WS without affecting behavior.</span></span>  
  
## <a name="export-restrictions-on-orchestrations-for-bpel4ws-compliance"></a><span data-ttu-id="1b8cf-107">オーケストレーションをエクスポートする際の制約 (BPEL4WS 準拠)</span><span class="sxs-lookup"><span data-stu-id="1b8cf-107">Export restrictions on orchestrations for BPEL4WS compliance</span></span>  
  
-   <span data-ttu-id="1b8cf-108">オーケストレーションの呼び出し図形とオーケストレーションの開始図形は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-108">You cannot use the Call Orchestration shape or the Start Orchestration shape.</span></span>  
  
-   <span data-ttu-id="1b8cf-109">変換図形は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-109">You cannot use the Transform shape.</span></span>  
  
-   <span data-ttu-id="1b8cf-110">カスタム .NET コンポーネントのメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-110">You cannot invoke methods on custom .NET components.</span></span>  
  
-   <span data-ttu-id="1b8cf-111">長時間実行されるトランザクションにはタイムアウトを適用できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-111">You cannot apply a timeout to a long-running transaction.</span></span>  
  
-   <span data-ttu-id="1b8cf-112">パラメーターを受け取るオーケストレーションはエクスポートできません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-112">Your orchestration cannot take parameters.</span></span>  
  
-   <span data-ttu-id="1b8cf-113">呼び出し可能な補正ハンドラーにパラメーターを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-113">Callable compensation handlers cannot have parameters.</span></span>  
  
-   <span data-ttu-id="1b8cf-114">変数の型が XPATH でサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-114">Variable types must be supportable in XPATH.</span></span>  
  
-   <span data-ttu-id="1b8cf-115">中断図形は使用できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-115">You cannot use the Suspend shape.</span></span>  
  
-   <span data-ttu-id="1b8cf-116">リテラル値は、次のいずれかの型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-116">Literal values must be one of the following types:</span></span>  
  
     <span data-ttu-id="1b8cf-117">boolean、char、byte、sbyte、int32、uint32、int64、uint64、single、double、string</span><span class="sxs-lookup"><span data-stu-id="1b8cf-117">boolean, char, byte, sbyte, int32, uint32, int64, uint64, single, double, string</span></span>  
  
-   <span data-ttu-id="1b8cf-118">算術演算子では、次の数値型のオペランドのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-118">Arithmetic operators are allowed only on operands of following numeric types:</span></span>  
  
     <span data-ttu-id="1b8cf-119">byte、sbyte、int32、uint32、int64、uint64、single、double</span><span class="sxs-lookup"><span data-stu-id="1b8cf-119">byte, sbyte, int32, uint32, int64, uint64, single, double</span></span>  
  
-   <span data-ttu-id="1b8cf-120">関係演算子を char 型には適用できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-120">Relational operators cannot be applied to type char.</span></span>  
  
-   <span data-ttu-id="1b8cf-121">式の中では servicelink プロパティを参照できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-121">You cannot make a reference to a servicelink property in an expression.</span></span>  
  
-   <span data-ttu-id="1b8cf-122">間のすべてのアクションを実行することはできません、**送信**図形および**受信**同じ要求-応答の送信ポートを使用する図形です。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-122">You cannot perform any actions between a **Send** shape and a **Receive** shape that use the same outbound request-response port.</span></span>  
  
-   <span data-ttu-id="1b8cf-123">特定の参照を保持する別のプロジェクトを参照するなどして、Web サービスを間接的に参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-123">You cannot indirectly reference a web service, as through a reference to another project that contains a reference.</span></span> <span data-ttu-id="1b8cf-124">プロジェクト内で Web サービスを明示的に参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-124">You must explicitly reference the web service in your project.</span></span>  
  
-   <span data-ttu-id="1b8cf-125">定数 DateTime や TimeSpan を指定して遅延を定義できません。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-125">You cannot specify a constant DateTime or TimeSpan in a delay.</span></span> <span data-ttu-id="1b8cf-126">System.Xml 名前空間のいずれかの変換クラスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-126">Instead, use one of the conversion classes in the System.Xml namespace:</span></span>  
  
     <span data-ttu-id="1b8cf-127">定数 DateTime の場合: System.Xml.XmlConvert.ToDateTime、System.Xml.XmlConvert.ToDateTime("2004-04-15") 例。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-127">For a constant DateTime: System.Xml.XmlConvert.ToDateTime, e.g System.Xml.XmlConvert.ToDateTime("2004-04-15")</span></span>  
  
     <span data-ttu-id="1b8cf-128">定数 TimeSpan の場合: System.Xml.XmlConvert.ToTimeSpan System.Xml.XmlConvert.ToTimeSpan("2004-04-15") 例。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-128">For a constant TimeSpan: System.Xml.XmlConvert.ToTimeSpan, e.g System.Xml.XmlConvert.ToTimeSpan("2004-04-15")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b8cf-129">文字リテラルは、符号なし整数としてエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-129">Character literals are exported as unsigned integers.</span></span> <span data-ttu-id="1b8cf-130">たとえば、'a' は 97 のように、'b' は 98 のようにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-130">For example, 'a' is exported as 97, 'b' is exported as 98, and so forth.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1b8cf-131">識別子の名前は、W3C Extensible Markup Language (XML) 1.0 仕様に準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-131">Identifier names must conform to the W3C Extensible Markup Language (XML) 1.0 specification.</span></span>  
  
#### <a name="to-export-an-orchestration-to-bpel4ws"></a><span data-ttu-id="1b8cf-132">オーケストレーションを BPEL4WS にエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="1b8cf-132">To export an orchestration to BPEL4WS</span></span>  
  
1.  <span data-ttu-id="1b8cf-133">プロジェクトに新しい項目 (BizTalk オーケストレーション) を追加します。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-133">Add a new item of type BizTalk Orchestration to your project.</span></span>  
  
2.  <span data-ttu-id="1b8cf-134">デザイン画面をクリックして、[オーケストレーションのプロパティ] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-134">Click the design surface to bring up the Orchestration Properties window.</span></span>  
  
3.  <span data-ttu-id="1b8cf-135">設定**モジュールがエクスポート可能**True に設定します。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-135">Set **Module Exportable** to True.</span></span>  
  
4.  <span data-ttu-id="1b8cf-136">名前空間の型**モジュール XML ターゲットの Namespace**です。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-136">Type in the namespace you want for **Module XML Target Namespace**.</span></span>  
  
5.  <span data-ttu-id="1b8cf-137">設定**エクスポート可能なオーケストレーション**True に設定します。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-137">Set **Orchestration Exportable** to True.</span></span>  
  
6.  <span data-ttu-id="1b8cf-138">名前空間の型**オーケストレーション XML Target Namespace**です。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-138">Type in the namespace you want for **Orchestration XML Target Namespace**.</span></span>  
  
7.  <span data-ttu-id="1b8cf-139">ソリューション エクスプ ローラーで右クリックします。オーケストレーションの ODX ファイルです。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-139">In Solution Explorer, right-click the .ODX file for your orchestration.</span></span>  
  
8.  <span data-ttu-id="1b8cf-140">選択**BPEL にエクスポート**です。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-140">Select **Export to BPEL**.</span></span>  
  
     <span data-ttu-id="1b8cf-141">オーケストレーションが BPEL4WS にエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-141">Your orchestration will be exported to BPEL4WS.</span></span> <span data-ttu-id="1b8cf-142">出力ウィンドウとタスク一覧を調べて、処理が正常に行われたかどうかを確認し、必要に応じて問題を診断します。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-142">See the Output Window and Task List to confirm success or diagnose problems.</span></span> <span data-ttu-id="1b8cf-143">エクスポートに成功すると、プロジェクト ディレクトリに .WSDL ファイルおよび .BPEL ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-143">Once your export succeeds, a .WSDL file and a .BPEL file will be created in your project directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b8cf-144">オーケストレーションにロール リンク (サービス リンク) に対する割り当てや、動的ポートへのリテラル割り当てが含まれる場合、BizTalk により、ダミーの BPEL4WS エンドポイント参照が生成され、警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="1b8cf-144">If your orchestration contains an assignment to a role link (service link) or a literal assignment to a dynamic port, BizTalk generates a dummy BPEL4WS endpoint reference and raises a warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8cf-145">参照</span><span class="sxs-lookup"><span data-stu-id="1b8cf-145">See Also</span></span>  
 <span data-ttu-id="1b8cf-146">[BPEL4WS をインポートする方法](../core/how-to-import-bpel4ws.md) </span><span class="sxs-lookup"><span data-stu-id="1b8cf-146">[How to Import BPEL4WS](../core/how-to-import-bpel4ws.md) </span></span>  
 [<span data-ttu-id="1b8cf-147">XLANG-s BPEL4WS 型への変換から</span><span class="sxs-lookup"><span data-stu-id="1b8cf-147">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)