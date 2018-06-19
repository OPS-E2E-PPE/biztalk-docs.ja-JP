---
title: XML 検証ステージ (回復可能なインターチェンジ処理) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ed00971-d85b-4adb-86c4-c56de7ba7c67
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8f0225e100053fe6dced8165b7fc800c5e4804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289954"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a><span data-ttu-id="fcb50-102">XML 検証ステージ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="fcb50-102">XML Validation Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="fcb50-103">**XML 検証**パイプライン コンポーネントは、2 つのモードでインターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="fcb50-103">The **XML validator** pipeline component processes an interchange in two modes:</span></span>  
  
-   <span data-ttu-id="fcb50-104">**標準モード**です。</span><span class="sxs-lookup"><span data-stu-id="fcb50-104">**Standard mode**.</span></span> <span data-ttu-id="fcb50-105">ときに、 **XML 検証**標準の検証を実行するコンポーネントが構成されて、インターチェンジに含まれているメッセージがトランザクションの作業単位で検証されます。</span><span class="sxs-lookup"><span data-stu-id="fcb50-105">When the **XML validator** component is configured to perform standard validation, the messages contained in an interchange are validated in a transactional unit of work.</span></span> <span data-ttu-id="fcb50-106">特に、インターチェンジのメッセージの検証に失敗した場合、すべてのメッセージを含むインターチェンジ全体が保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="fcb50-106">Specifically, if validation of a message in the interchange fails, the entire interchange (containing all the messages) is placed in the suspended queue.</span></span>  
  
-   <span data-ttu-id="fcb50-107">**回復可能なモード**です。</span><span class="sxs-lookup"><span data-stu-id="fcb50-107">**Recoverable mode**.</span></span> <span data-ttu-id="fcb50-108">ときに、 **XML 検証**コンポーネントが構成されているを実行する回復可能なインターチェンジを処理するメッセージの検証が失敗した場合、メッセージが保留キューに配置され、 **XML 検証**コンポーネントは、インターチェンジの残りのメッセージの検証を続行します。</span><span class="sxs-lookup"><span data-stu-id="fcb50-108">When the **XML validator** component is configured to perform recoverable interchange processing, if validation of a message fails, the message is placed in the suspended queue and the **XML validator** component continues to validate remaining messages in the interchange.</span></span>  
  
### <a name="to-configure-recoverable-interchange-processing"></a><span data-ttu-id="fcb50-109">回復可能なインターチェンジ処理を構成するには</span><span class="sxs-lookup"><span data-stu-id="fcb50-109">To configure recoverable interchange processing</span></span>  
  
1.  <span data-ttu-id="fcb50-110">Visual Studio でパイプライン デザイナーを使用して受信パイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="fcb50-110">Open a receive pipeline by using pipeline designer in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="fcb50-111">ドラッグ**XML 検証**のコンポーネント、**ツールボックス**を**検証**受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="fcb50-111">Drag **XML validator** component from the **Toolbox** to the **Validate** stage of the receive pipeline.</span></span>  
  
3.  <span data-ttu-id="fcb50-112">[プロパティ] ウィンドウ内の値を設定、**回復可能なインターチェンジ処理**プロパティを**True**する場合は、 **XML 検証**コンポーネント プロセス インターチェンジを回復可能なモードでプロパティを設定または**False**コンポーネント、標準モードでインターチェンジを処理する場合。</span><span class="sxs-lookup"><span data-stu-id="fcb50-112">In the Properties window, set the value of the **Recoverable Interchange Processing** property to **True** if you want the **XML validator** component to process interchanges in the recoverable mode, or set the property to **False** if you want the component to process interchanges in the standard mode.</span></span> <span data-ttu-id="fcb50-113">このプロパティの既定値は`False`します。</span><span class="sxs-lookup"><span data-stu-id="fcb50-113">The default value of this property is `False`.</span></span>  
  
 <span data-ttu-id="fcb50-114">**XMLValidator**に対応するオブジェクト モデル内のクラス、 **XML 検証**パイプライン コンポーネント、という名前のパブリック プロパティには**RecoverableInterchangeProcessing**を取得または設定モード プログラムで使用することできます。</span><span class="sxs-lookup"><span data-stu-id="fcb50-114">The **XMLValidator** class in the object model, which corresponds to the **XML validator** pipeline component, has a public property named **RecoverableInterchangeProcessing** that you can use to get/set the mode programmatically.</span></span> <span data-ttu-id="fcb50-115">ドキュメントを参照して[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)詳細情報のクラスです。</span><span class="sxs-lookup"><span data-stu-id="fcb50-115">See documentation for [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) class for more information.</span></span>  
  
 <span data-ttu-id="fcb50-116">検証に成功したメッセージは、親のインターチェンジが到着する受信ポートに対して構成されているパーティに応じて、送信するパーティを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcb50-116">Messages that are successfully validated have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="fcb50-117">インターチェンジから抽出されたメッセージでパーティの解決が失敗した場合、パーティの解決は、インターチェンジ全体で失敗したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="fcb50-117">If party resolution for any message extracted from the interchange fails, then the party resolution is considered to have failed for the entire interchange.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb50-118">参照</span><span class="sxs-lookup"><span data-stu-id="fcb50-118">See Also</span></span>  
 [<span data-ttu-id="fcb50-119">XML 検証パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="fcb50-119">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)