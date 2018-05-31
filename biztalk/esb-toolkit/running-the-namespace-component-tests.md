---
title: Namespace コンポーネントのテストを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae865e91fd6ff796cb870c71840bde8a95831e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294938"
---
# <a name="running-the-namespace-component-tests"></a><span data-ttu-id="d9f18-102">Namespace コンポーネントのテストを実行しています。</span><span class="sxs-lookup"><span data-stu-id="d9f18-102">Running the Namespace Component Tests</span></span>
<span data-ttu-id="d9f18-103">次の手順は 4 つのテスト シナリオのすべてを実行する方法を示しています、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Namespace コンポーネント サンプルです。</span><span class="sxs-lookup"><span data-stu-id="d9f18-103">The following procedure shows how you can run all four of the test scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Namespace Component sample.</span></span>  
  
 <span data-ttu-id="d9f18-104">**Namespace コンポーネント サンプルのテストのシナリオを実行するには**</span><span class="sxs-lookup"><span data-stu-id="d9f18-104">**To run the Namespace Component sample test scenarios**</span></span>  
  
1.  <span data-ttu-id="d9f18-105">最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指しているソース配布ファイルに適切なサブフォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-105">Before you run this sample for the first time, make sure that the receive location and send port URL point to the appropriate subfolders in the source distribution files.</span></span> <span data-ttu-id="d9f18-106">受信場所のサブフォルダー \Source\Samples\Namespace\Test\Filedrop\In とサブフォルダー \Source\Samples\Namespace\Test\Filedrop\Out 送信ポートの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-106">Specify the subfolder \Source\Samples\Namespace\Test\Filedrop\In for the receive location and the subfolder \Source\Samples\Namespace\Test\Filedrop\Out for the send port URL.</span></span>  
  
2.  <span data-ttu-id="d9f18-107">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-107">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
3.  <span data-ttu-id="d9f18-108">(ESB インストール フォルダーの \Source\Samples\Namespace\Test\Data\ サブフォルダーにあります)、TEST_Add_to_PassThrough.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで、コピーの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-108">Make a copy of the file named TEST_Add_to_PassThrough.0000.ns.xml (located in the \Source\Samples\Namespace\Test\Data\ subfolder of your ESB installation folder), and rename the copy by removing the "TEST_" prefix.</span></span>  
  
4.  <span data-ttu-id="d9f18-109">\Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-109">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
5.  <span data-ttu-id="d9f18-110">ESB は、メッセージを取得、名前空間を追加し、\Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに、更新されたメッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-110">The ESB picks up the message, adds a namespace to it, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="d9f18-111">入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-111">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
6.  <span data-ttu-id="d9f18-112">2 つ目のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-112">Now run the second test.</span></span> <span data-ttu-id="d9f18-113">TEST_Add_to_Remove.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-113">Make a copy of the file named TEST_Add_to_Remove.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
7.  <span data-ttu-id="d9f18-114">\Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-114">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
8.  <span data-ttu-id="d9f18-115">ESB は、メッセージを取得、名前空間を追加、新しい名前空間を削除、および \Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに、更新されたメッセージをドロップをします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-115">The ESB picks up the message, adds a namespace to it, removes the new namespace, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="d9f18-116">入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-116">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
9. <span data-ttu-id="d9f18-117">3 番目のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-117">Now run the third test.</span></span> <span data-ttu-id="d9f18-118">TEST_PassThrough_to_Remove.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-118">Make a copy of the file named TEST_PassThrough_to_Remove.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
10. <span data-ttu-id="d9f18-119">\Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-119">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
11. <span data-ttu-id="d9f18-120">ESB は、メッセージを取得、既存の名前空間を削除し、\Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに、更新されたメッセージをドロップします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-120">The ESB picks up the message, removes the existing namespace, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="d9f18-121">入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-121">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
12. <span data-ttu-id="d9f18-122">最後に、4 つ目のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-122">Finally, run the fourth test.</span></span> <span data-ttu-id="d9f18-123">TEST_AddViaExtraction_to_PassThrough.0000.ns.xml をという名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-123">Make a copy of the file named TEST_AddViaExtraction_to_PassThrough.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
13. <span data-ttu-id="d9f18-124">\Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d9f18-124">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
14. <span data-ttu-id="d9f18-125">ESB は、メッセージを取得で指定された要素を抽出し、 **ExtractionNodeXPath**プロパティがこの要素で指定された名前空間の値からメッセージを作成し、\Source\Samples\ に更新されたメッセージをドロップします。Namespace\Test\Filedrop\Out サブフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d9f18-125">The ESB picks up the message, extracts the element specified in the **ExtractionNodeXPath** property, creates a message from this element with the specified namespace values, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="d9f18-126">入力を開き、このテストの結果を確認するためのテキスト エディターでファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="d9f18-126">Open the input and output files in a text editor to see the effect of this test.</span></span>