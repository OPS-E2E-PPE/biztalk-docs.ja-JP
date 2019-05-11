---
title: フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adc27561-9996-49a9-b715-e313b9148506
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f975f04bb18dca5cc8e311fdb21d7b44caf01d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322132"
---
# <a name="retaining-delimiters-in-the-flat-file-assembler-pipeline-component"></a><span data-ttu-id="e6970-102">フラット ファイル アセンブラー パイプライン コンポーネントの区切り記号の保持</span><span class="sxs-lookup"><span data-stu-id="e6970-102">Retaining Delimiters in the Flat File Assembler Pipeline Component</span></span>
<span data-ttu-id="e6970-103">フラット ファイル アセンブラーを使用するカスタム パイプラインを通過するメッセージに不足しているレコードがある場合、そのレコードの区切り記号は可能性があります。 またはによっては、入力ファイル内のレコードが不足しているフラット ファイルの出力が表示されません。</span><span class="sxs-lookup"><span data-stu-id="e6970-103">If there are missing records in the message going through a custom pipeline that uses the Flat File Assembler, the delimiter for those records may or may not appear in the flat file output depending on where in the input file the records are missing.</span></span>  
  
 <span data-ttu-id="e6970-104">ように、特定の区切り記号を保持するフラット ファイルを確認する、マップとカスタム スクリプトを使用することができます、メッセージでは、特定の入力レコードが存在しない場合は、「空」のレコードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6970-104">To ensure that the flat file retain certain delimiters, you can use a map and a custom script to make sure an "empty" record is created when a specific input record does not exist in the message.</span></span> <span data-ttu-id="e6970-105">これを機能させるには、フラット ファイル アセンブラーのドキュメント スキーマの可能性がある空のノードが示すように設定する次のプロパティであることの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6970-105">For this to work, you must make sure that the potentially empty nodes in the document schema for the Flat File Assembler have the following properties set as shown:</span></span>  
  
|<span data-ttu-id="e6970-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e6970-106">Property</span></span>|<span data-ttu-id="e6970-107">設定</span><span class="sxs-lookup"><span data-stu-id="e6970-107">Setting</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="e6970-108">空のデータの区切り記号を保存します。</span><span class="sxs-lookup"><span data-stu-id="e6970-108">Preserve Delimiter for Empty Data</span></span>|<span data-ttu-id="e6970-109">はい</span><span class="sxs-lookup"><span data-stu-id="e6970-109">Yes</span></span>|  
|<span data-ttu-id="e6970-110">末尾の区切り記号を非表示します。</span><span class="sxs-lookup"><span data-stu-id="e6970-110">Suppress Trailing Delimiters</span></span>|<span data-ttu-id="e6970-111">いいえ</span><span class="sxs-lookup"><span data-stu-id="e6970-111">No</span></span>|  
|<span data-ttu-id="e6970-112">空のノードの生成 (ルート ノードの設定)</span><span class="sxs-lookup"><span data-stu-id="e6970-112">Generate Empty Nodes (set this on the root node)</span></span>|<span data-ttu-id="e6970-113">True</span><span class="sxs-lookup"><span data-stu-id="e6970-113">True</span></span>|  
  
### <a name="to-create-a-map-that-creates-an-empty-record"></a><span data-ttu-id="e6970-114">「空」のレコードを作成するマップを作成するには</span><span class="sxs-lookup"><span data-stu-id="e6970-114">To create a map that creates an "empty" record</span></span>  
  
1.  <span data-ttu-id="e6970-115">新しいマップを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="e6970-115">Add a new map to your BizTalk project.</span></span>  
  
2.  <span data-ttu-id="e6970-116">マップの送信元と送信先スキーマのマップの両方として、フラット ファイル アセンブラーで使用されるドキュメント スキーマを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6970-116">Specify the document schema used by the Flat File Assembler as both the map source and map destination schema.</span></span>  
  
3.  <span data-ttu-id="e6970-117">対応する先のフィールドを空にならないソース フィールドをマップします。</span><span class="sxs-lookup"><span data-stu-id="e6970-117">Map the source fields that will not be empty to the corresponding destination fields.</span></span>  
  
4.  <span data-ttu-id="e6970-118">空にすることをこれらのフィールドに対してカスタム スクリプトを使用して、ソース フィールドが空かを確認し、(Nil) ではなく空の文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="e6970-118">For those fields that may be empty, use a custom script to check if the source field is empty and return an empty string (instead of Nil).</span></span> <span data-ttu-id="e6970-119">次のようなスクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="e6970-119">Use a script like the following:</span></span>  
  
    ```  
    public string ValOrEmpty(string val)  
    {  
         return (val.Length > 0) ? val : "";  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="e6970-120">マップする可能性がある空のフィールドごとに一意の関数の名前は、スクリプトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6970-120">You must create a script with a unique function name for each potentially empty field you map.</span></span> <span data-ttu-id="e6970-121">たとえば、3 つのフィールドが空になる可能性がある場合は、という名前の関数を必要があります`ValOrEmpty1`、 `ValOrEmpty2`、`ValOrEmpty3`します。</span><span class="sxs-lookup"><span data-stu-id="e6970-121">For example, if you have three fields that may be empty, you might have functions named `ValOrEmpty1`, `ValOrEmpty2`, `ValOrEmpty3`.</span></span>  
  
5.  <span data-ttu-id="e6970-122">BizTalk Server 管理コンソールを使用して、カスタム パイプラインと送信マップとしてマップを使用するフラット ファイル アセンブラー コンポーネントでの送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="e6970-122">Using BizTalk Server Administration console, configure the send port with the custom pipeline and flat file assembler component to use the map as an outbound map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6970-123">参照</span><span class="sxs-lookup"><span data-stu-id="e6970-123">See Also</span></span>  
 <span data-ttu-id="e6970-124">[送信ポートの送信マップを構成する方法](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span><span class="sxs-lookup"><span data-stu-id="e6970-124">[How to Configure Outbound Maps for a Send Port](../core/how-to-configure-outbound-maps-for-a-send-port.md) </span></span>  
 [<span data-ttu-id="e6970-125">フラット ファイル アセンブラー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e6970-125">Flat File Assembler Pipeline Component</span></span>](../core/flat-file-assembler-pipeline-component.md)