---
title: "フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9d10879adfbe0ca0c68376faa48d9976fc19599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="f4b5f-102">フラット ファイル アセンブラー パイプライン コンポーネントでの区切り記号の保持</span><span class="sxs-lookup"><span data-stu-id="f4b5f-102">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="f4b5f-103">フラット ファイル アセンブラーを使用するカスタム パイプラインを通るメッセージに、レコードが不足している場合、フラット ファイルの出力にレコードの区切り記号が表示されるかどうかは、入力ファイルのどこでレコードが不足しているかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-103">If there are missing records in the message going through a custom pipeline that uses the Flat File Assembler, the delimiter for those records may or may not appear in the flat file output depending on where in the input file the records are missing.</span></span>  
  
 <span data-ttu-id="f4b5f-104">フラット ファイルに特定の区切り記号が保持されるようにするには、マップとカスタム スクリプトを使用できます。これにより、特定の入力レコードがメッセージ内に存在しないときに "空の" レコードが確実に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-104">To ensure that the flat file retain certain delimiters, you can use a map and a custom script to make sure an "empty" record is created when a specific input record does not exist in the message.</span></span> <span data-ttu-id="f4b5f-105">これが機能するためには、フラット ファイル アセンブラーのドキュメント スキーマで空になる可能性があるノードに、次のようにプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-105">For this to work, you must make sure that the potentially empty nodes in the document schema for the Flat File Assembler have the following properties set as shown:</span></span>  
  
|<span data-ttu-id="f4b5f-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f4b5f-106">Property</span></span>|<span data-ttu-id="f4b5f-107">設定</span><span class="sxs-lookup"><span data-stu-id="f4b5f-107">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="f4b5f-108">空のデータの区切り記号を保存します。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-108">Preserve Delimiter for Empty Data</span></span>|<span data-ttu-id="f4b5f-109">はい</span><span class="sxs-lookup"><span data-stu-id="f4b5f-109">Yes</span></span>|  
|<span data-ttu-id="f4b5f-110">末尾の区切り記号の非表示</span><span class="sxs-lookup"><span data-stu-id="f4b5f-110">Suppress Trailing Delimiters</span></span>|<span data-ttu-id="f4b5f-111">不可</span><span class="sxs-lookup"><span data-stu-id="f4b5f-111">No</span></span>|  
|<span data-ttu-id="f4b5f-112">空のノードを生成 (ルート ノードに設定)</span><span class="sxs-lookup"><span data-stu-id="f4b5f-112">Generate Empty Nodes (set this on the root node)</span></span>|<span data-ttu-id="f4b5f-113">True</span><span class="sxs-lookup"><span data-stu-id="f4b5f-113">True</span></span>|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a><span data-ttu-id="f4b5f-114">"空の" レコードを作成するマップを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4b5f-114">To create a map that creates an "empty" record</span></span>  
  
1.  <span data-ttu-id="f4b5f-115">BizTalk プロジェクトに新しいマップを追加します。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-115">Add a new map to your BizTalk project.</span></span>  
  
2.  <span data-ttu-id="f4b5f-116">フラット ファイル アセンブラーによって使用されるドキュメント スキーマを、マップの送信元スキーマと送信先スキーマの両方に指定します。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-116">Specify the document schema used by the Flat File Assembler as both the map source and map destination schema.</span></span>  
  
3.  <span data-ttu-id="f4b5f-117">空にならないソース フィールドを、対応するマップ先フィールドにマップします。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-117">Map the source fields that will not be empty to the corresponding destination fields.</span></span>  
  
4.  <span data-ttu-id="f4b5f-118">空になる可能性があるフィールドに対しては、ソース フィールドが空であるかどうかを確認して (Nil の代わりに) 空の文字列を返すカスタム スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-118">For those fields that may be empty, use a custom script to check if the source field is empty and return an empty string (instead of Nil).</span></span> <span data-ttu-id="f4b5f-119">次のようなスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-119">Use a script like the following:</span></span>  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f4b5f-120">空になる可能性があるマップ対象フィールドごとに、一意の関数名を持つスクリプトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-120">You must create a script with a unique function name for each potentially empty field you map.</span></span> <span data-ttu-id="f4b5f-121">たとえば、空になる可能性があるフィールドが 3 つある場合、`ValOrEmpty1`、`ValOrEmpty2`、および `ValOrEmpty3` という名前の関数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-121">For example, if you have three fields that may be empty, you might have functions named `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.</span></span>  
  
5.  <span data-ttu-id="f4b5f-122">カスタム パイプラインと送信マップとしてマップを使用するフラット ファイル アセンブラー コンポーネントでの送信ポートを構成する BizTalk Server 管理コンソールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4b5f-122">Using BizTalk Server Administration console, configure the send port with the custom pipeline and flat file assembler component to use the map as an outbound map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b5f-123">参照</span><span class="sxs-lookup"><span data-stu-id="f4b5f-123">See Also</span></span>  
 <span data-ttu-id="f4b5f-124">[送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="f4b5f-124">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="f4b5f-125">フラット ファイル アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f4b5f-125">Flat File Assembler Pipeline Component</span></span>](../core/flat-file-assembler-pipeline-component.md)