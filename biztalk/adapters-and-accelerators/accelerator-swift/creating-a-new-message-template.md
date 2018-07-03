---
title: 新しいメッセージ テンプレートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, templates
- templates, creating
- creating, templates
ms.assetid: 8c601d2b-b7a5-4ac4-9d98-fd9960038340
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e89c34b29818ab053217b823c6f8a787ce50a15d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999835"
---
# <a name="creating-a-new-message-template"></a><span data-ttu-id="55fb0-102">新しいメッセージ テンプレートの作成</span><span class="sxs-lookup"><span data-stu-id="55fb0-102">Creating a New Message Template</span></span>
<span data-ttu-id="55fb0-103">既存のテンプレートから新しいメッセージ テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="55fb0-103">You can create a new message template from an existing template.</span></span> <span data-ttu-id="55fb0-104">これにより、作成者が既に一部のデータが入力されている標準の SWIFT フォームのコピーなどのカスタム フォームで新しいメッセージ インスタンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="55fb0-104">This enables a creator to create a new message instance on a custom form, such as a copy of a standard SWIFT form that already has some data entered into it.</span></span> <span data-ttu-id="55fb0-105">新しいテンプレートを使用して、作成者は、する必要はありませんすべての空のフォームを使用する場合に必要なデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-105">Using the new template, the creator does not have to enter all of the data required when using an empty form.</span></span>  
  
 <span data-ttu-id="55fb0-106">生成されて、対応する既存のテンプレートを使用しているメッセージ インスタンスから新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-106">You create a new template from a message instance that you have generated using the corresponding existing template.</span></span> <span data-ttu-id="55fb0-107">データのフィールドを追加する、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] (よう、新しいメッセージ インスタンスを作成する) を形成するには、し、新しいテンプレートとしてフォームを保存します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-107">You add data to the fields of the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form (as though you were creating a new message instance), and then save the form as a new template.</span></span>  
  
### <a name="to-save-a-modified-existing-template-as-a-new-template"></a><span data-ttu-id="55fb0-108">変更された既存のテンプレートを新しいテンプレートとして保存するには</span><span class="sxs-lookup"><span data-stu-id="55fb0-108">To save a modified existing template as a new template</span></span>  
  
1. <span data-ttu-id="55fb0-109">Internet Explorer で、開く、MRSR サイトがhttp://localhost/sites/bassiteします。</span><span class="sxs-lookup"><span data-stu-id="55fb0-109">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2. <span data-ttu-id="55fb0-110">**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fb0-110">Click **Documents**.</span></span>  
  
3. <span data-ttu-id="55fb0-111">[ドキュメント] ページで、をクリックして、**新しい SWIFT MT メッセージ**ドキュメント ライブラリです。</span><span class="sxs-lookup"><span data-stu-id="55fb0-111">On the Documents page, click the **New SWIFT MT Messages** document library.</span></span>  
  
4. <span data-ttu-id="55fb0-112">新しい SWIFT MT メッセージ ページで、新しいテンプレートを基にテンプレートを格納しているカテゴリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fb0-112">On the New SWIFT MT Messages page, click the category containing the template that you want to base your new template on.</span></span>  
  
5. <span data-ttu-id="55fb0-113">新しいテンプレートの作成で、右矢印をクリックしてをクリックしたいテンプレートを指す**Microsoft Office InfoPath で編集**します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-113">Point to the template that you want to base your new template on, click the arrow to the right, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6. <span data-ttu-id="55fb0-114">[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007年ウィンドウで、メッセージの形式で、テンプレートの一部にするメッセージ データを入力します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-114">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, in the message form, enter message data that you want to be part of the template.</span></span>  
  
7. <span data-ttu-id="55fb0-115">クリックして**ファイル**、 をクリックし、**名前を付けて保存**します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-115">Click **File**, and then click **Save As**.</span></span>  
  
8. <span data-ttu-id="55fb0-116">内に、ポップアップを示す、フォームに検証エラーが含まれている、次のようにクリックします。**はい**します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-116">In the popup indicating that the form contains validation errors, click **Yes**.</span></span>  
  
9. <span data-ttu-id="55fb0-117">名前を付けて保存 ダイアログ ボックスで、テンプレートのフォルダーを選択、**で保存**テキスト ボックス、およびファイルの名前を入力し、**ファイル名**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="55fb0-117">In the Save As dialog box, select the folder for the template in the **Save in** text box, and then enter a file name in the **File name** text box.</span></span> <span data-ttu-id="55fb0-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="55fb0-118">Click **Save**.</span></span>  
  
10. <span data-ttu-id="55fb0-119">閉じる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]新しいテンプレートの形式。</span><span class="sxs-lookup"><span data-stu-id="55fb0-119">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for the new template.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55fb0-120">新しいテンプレートからのメッセージ インスタンスを作成するを参照してください。[を作成すると、新しいメッセージを送信する](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="55fb0-120">To create a message instance from the new template, see [Creating and Submitting a New Message](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md).</span></span>