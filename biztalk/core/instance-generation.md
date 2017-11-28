---
title: "インスタンスの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14060dca-5e14-474a-bf2c-4e8bc56e3c61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bd3d2bc6852ec0c73fbbe4ffc55924a8012ce5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="instance-generation"></a><span data-ttu-id="cb8fa-102">インスタンスの生成</span><span class="sxs-lookup"><span data-stu-id="cb8fa-102">Instance Generation</span></span>
<span data-ttu-id="cb8fa-103">BizTalk エディターを起動、 **IInstanceGenerator.GenerateInstance**次の条件が満たされたときに、拡張機能のメソッド。</span><span class="sxs-lookup"><span data-stu-id="cb8fa-103">BizTalk Editor invokes the **IInstanceGenerator.GenerateInstance** method of an extension when the following conditions are met:</span></span>  
  
-   <span data-ttu-id="cb8fa-104">使用して、拡張機能が設定の標準として、**標準**のプロパティ、**スキーマ**ノード。</span><span class="sxs-lookup"><span data-stu-id="cb8fa-104">The extension is set as standard by using the **Standard** property of the **Schema** node.</span></span>  
  
-   <span data-ttu-id="cb8fa-105">**プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられている、**インスタンスの出力の種類の生成**プロパティに設定されている**ネイティブです。**</span><span class="sxs-lookup"><span data-stu-id="cb8fa-105">On the **Property Pages** dialog box associated with the schema, the **Generate Instance Output Type** property is set to **Native.**</span></span>  
  
-   <span data-ttu-id="cb8fa-106">**プロパティ ページ** ダイアログ ボックスが、スキーマに関連付けられている、**出力インスタンス ファイル名**プロパティが、出力インスタンスに保存されるファイルの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="cb8fa-106">On the **Property Pages** dialog box associated with the schema, the **Output Instance Filename** property is set to the name of the file that the output instance will be saved to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb8fa-107">場合、**出力インスタンス ファイル名**プロパティが設定されていない、一時フォルダーの既定のファイル名が生成されたインスタンス メッセージの使用およびへのリンクは、出力ウィンドウに提供します。</span><span class="sxs-lookup"><span data-stu-id="cb8fa-107">If the **Output Instance Filename** property is not set, a default file name in a temporary folder is used for the generated instance message, and a link to it is provided in the Output window.</span></span>  
  
 <span data-ttu-id="cb8fa-108">前に、 **IInstanceValidator.ValidateInstance**で指定されたファイルと、BizTalk エディターは、サンプル XML インスタンス メッセージを生成し、それを渡しますメソッドが呼び出される、**出力インスタンス ファイル名**プロパティ、またはそのメソッドに、既定のファイル名。</span><span class="sxs-lookup"><span data-stu-id="cb8fa-108">Before the **IInstanceValidator.ValidateInstance** method is called, BizTalk Editor generates a sample XML instance message, and then passes it and the file specified in the **Output Instance Filename** property, or a default file name, to that method.</span></span>  
  
 <span data-ttu-id="cb8fa-109">配列としてエラーが発生した場合のエラー メッセージが返されます**IValidationInfo**オブジェクト、およびに表示される、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]タスク一覧ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="cb8fa-109">If errors occur, error messages are returned as an array of **IValidationInfo** objects, and are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Task List window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb8fa-110">参照</span><span class="sxs-lookup"><span data-stu-id="cb8fa-110">See Also</span></span>  
 [<span data-ttu-id="cb8fa-111">BizTalk エディターの拡張</span><span class="sxs-lookup"><span data-stu-id="cb8fa-111">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)