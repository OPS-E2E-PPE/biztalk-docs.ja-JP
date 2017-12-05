---
title: "JMS MQRFH2 サンプルの依存関係と強力なキー名の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3a5cdce-dcdf-48df-91a5-8cf2afce9255
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f3e2f76a972f851322f82f2e89b285db907d799
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="jms-mqrfh2-sample-dependencies-and-strong-key-name-definition"></a><span data-ttu-id="45381-102">JMS MQRFH2 サンプルの依存関係と強力なキー名の定義</span><span class="sxs-lookup"><span data-stu-id="45381-102">JMS MQRFH2 Sample Dependencies and Strong Key Name Definition</span></span>
<span data-ttu-id="45381-103">Visual Studio プロジェクト ESB です。JMS です。PipelineComponents は、次のフォルダーに依存します。</span><span class="sxs-lookup"><span data-stu-id="45381-103">The Visual Studio project ESB.JMS.PipelineComponents depends on the following folder:</span></span>  
  
-   <span data-ttu-id="45381-104">\<BizTalk Server のインストール ディレクトリ\>です。</span><span class="sxs-lookup"><span data-stu-id="45381-104">\<BizTalk Server Installation Directory\>.</span></span> <span data-ttu-id="45381-105">このフォルダーは、次の名前空間へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="45381-105">This folder provides access to the following namespaces:</span></span>  
  
    -   <span data-ttu-id="45381-106">**Microsoft::BizTalk::Message::Interop**</span><span class="sxs-lookup"><span data-stu-id="45381-106">**Microsoft::BizTalk::Message::Interop**</span></span>  
  
    -   <span data-ttu-id="45381-107">**Microsoft::BizTalk::Component::Interop**</span><span class="sxs-lookup"><span data-stu-id="45381-107">**Microsoft::BizTalk::Component::Interop**</span></span>  
  
## <a name="the-strong-name-key-definition"></a><span data-ttu-id="45381-108">厳密な名前キーの定義</span><span class="sxs-lookup"><span data-stu-id="45381-108">The Strong Name Key Definition</span></span>  
 <span data-ttu-id="45381-109">通常、厳密な名前キーの定義は、AssemblyInfo.cpp ファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="45381-109">Usually, the strong-name key definition resides in the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="45381-110">ただし、AssemblyInfo.cpp ファイルの読み取り後に、コンパイラがアセンブリに追加された C++ マニフェスト ファイルと競合します。</span><span class="sxs-lookup"><span data-stu-id="45381-110">However, this would conflict with the C++ manifest file that the compiler adds to the assembly after it reads the AssemblyInfo.cpp file.</span></span> <span data-ttu-id="45381-111">この競合は、グローバル アセンブリ キャッシュにファイルを配置するあらゆる試みをできなくなります。</span><span class="sxs-lookup"><span data-stu-id="45381-111">This conflict would prevent any attempt to place the file in the global assembly cache.</span></span> <span data-ttu-id="45381-112">代わりに、リンカーにある、キー ファイルを指定することによって、厳密な名前キー ファイルを制御./../../../../../Keys/Microsoft.Practices.ESB.snk です。</span><span class="sxs-lookup"><span data-stu-id="45381-112">Instead, the linker controls the strong name key file by specifying the key file located at ../../../../../../Keys/Microsoft.Practices.ESB.snk.</span></span> <span data-ttu-id="45381-113">この値を編集するには、次のオプションの設定に移動します。</span><span class="sxs-lookup"><span data-stu-id="45381-113">To edit this value, navigate to the following option setting:</span></span>  
  
 <span data-ttu-id="45381-114">ESB です。JMS です。スキーマ</span><span class="sxs-lookup"><span data-stu-id="45381-114">ESB.JMS.Schemas</span></span>  
  
 <span data-ttu-id="45381-115">\- プロジェクト</span><span class="sxs-lookup"><span data-stu-id="45381-115">\- Project</span></span>  
  
 <span data-ttu-id="45381-116">\--プロパティ</span><span class="sxs-lookup"><span data-stu-id="45381-116">\- - Properties</span></span>  
  
 <span data-ttu-id="45381-117">\--構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="45381-117">\- - - Configuration Properties</span></span>  
  
 <span data-ttu-id="45381-118">\----リンカー</span><span class="sxs-lookup"><span data-stu-id="45381-118">\- - - - Linker</span></span>  
  
 <span data-ttu-id="45381-119">\-----詳細</span><span class="sxs-lookup"><span data-stu-id="45381-119">\- - - - - Advanced</span></span>  
  
 <span data-ttu-id="45381-120">\-含みますキー ファイル</span><span class="sxs-lookup"><span data-stu-id="45381-120">\- - - - - - Key File</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45381-121">JMS パイプライン コンポーネントを作成している場合は、前述のように、厳密な名前キー ファイルへの参照を削除する AssemblyInfo.cpp ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45381-121">If you construct a JMS Pipeline Component, you must edit the AssemblyInfo.cpp file to remove any references to the strong-name key file, as described earlier.</span></span> <span data-ttu-id="45381-122">コピー後、編集、**キー ファイル**リンカーの詳細プロパティのパスと厳密な名前キー ファイルの名前を指定するオプションです。</span><span class="sxs-lookup"><span data-stu-id="45381-122">After you do that, edit the **Key File** option in the advanced properties of the Linker to specify the path and name of the strong-name key file.</span></span>