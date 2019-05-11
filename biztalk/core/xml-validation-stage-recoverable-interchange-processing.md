---
title: XML 検証ステージ (回復可能なインターチェンジ処理) |Microsoft Docs
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
ms.openlocfilehash: 5c2aad27b00012972214e2d86ad78a871bb609fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401556"
---
# <a name="xml-validation-stage-recoverable-interchange-processing"></a><span data-ttu-id="b77c5-102">XML 検証ステージ (回復可能なインターチェンジ処理)</span><span class="sxs-lookup"><span data-stu-id="b77c5-102">XML Validation Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="b77c5-103">**XML validator**パイプライン コンポーネントは、2 つのモードでインターチェンジを処理します。</span><span class="sxs-lookup"><span data-stu-id="b77c5-103">The **XML validator** pipeline component processes an interchange in two modes:</span></span>  
  
-   <span data-ttu-id="b77c5-104">**標準モード**します。</span><span class="sxs-lookup"><span data-stu-id="b77c5-104">**Standard mode**.</span></span> <span data-ttu-id="b77c5-105">ときに、 **XML validator**標準の検証を実行するコンポーネントが構成されている、トランザクションの作業単位で、インターチェンジに含まれるメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="b77c5-105">When the **XML validator** component is configured to perform standard validation, the messages contained in an interchange are validated in a transactional unit of work.</span></span> <span data-ttu-id="b77c5-106">具体的には、インターチェンジ内のメッセージの検証が失敗した場合、インターチェンジ全体 (すべてのメッセージを含む) は保留キューに配置されます。</span><span class="sxs-lookup"><span data-stu-id="b77c5-106">Specifically, if validation of a message in the interchange fails, the entire interchange (containing all the messages) is placed in the suspended queue.</span></span>  
  
-   <span data-ttu-id="b77c5-107">**回復可能なモード**します。</span><span class="sxs-lookup"><span data-stu-id="b77c5-107">**Recoverable mode**.</span></span> <span data-ttu-id="b77c5-108">ときに、 **XML 検証**コンポーネントが構成されているを実行する回復可能なインターチェンジを処理するメッセージの検証が失敗した場合は、メッセージは保留キューに配置されます、 **XML validator**コンポーネントは、インターチェンジの残りのメッセージを検証し続けます。</span><span class="sxs-lookup"><span data-stu-id="b77c5-108">When the **XML validator** component is configured to perform recoverable interchange processing, if validation of a message fails, the message is placed in the suspended queue and the **XML validator** component continues to validate remaining messages in the interchange.</span></span>  
  
### <a name="to-configure-recoverable-interchange-processing"></a><span data-ttu-id="b77c5-109">回復可能なインターチェンジ処理を構成するには</span><span class="sxs-lookup"><span data-stu-id="b77c5-109">To configure recoverable interchange processing</span></span>  
  
1. <span data-ttu-id="b77c5-110">Visual Studio でパイプライン デザイナーを使用して、受信パイプラインを開きます。</span><span class="sxs-lookup"><span data-stu-id="b77c5-110">Open a receive pipeline by using pipeline designer in Visual Studio.</span></span>  
  
2. <span data-ttu-id="b77c5-111">ドラッグ**XML validator**コンポーネントから、**ツールボックス**を**検証**受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="b77c5-111">Drag **XML validator** component from the **Toolbox** to the **Validate** stage of the receive pipeline.</span></span>  
  
3. <span data-ttu-id="b77c5-112">[プロパティ] ウィンドウでの値を設定、**回復可能なインターチェンジ処理**プロパティを**True**する場合は、 **XML validator**コンポーネント プロセス インターチェンジを回復可能なモードでプロパティを設定または**False**コンポーネント、標準モードでインターチェンジを処理する場合。</span><span class="sxs-lookup"><span data-stu-id="b77c5-112">In the Properties window, set the value of the **Recoverable Interchange Processing** property to **True** if you want the **XML validator** component to process interchanges in the recoverable mode, or set the property to **False** if you want the component to process interchanges in the standard mode.</span></span> <span data-ttu-id="b77c5-113">このプロパティの既定値は `False` です。</span><span class="sxs-lookup"><span data-stu-id="b77c5-113">The default value of this property is `False`.</span></span>  
  
   <span data-ttu-id="b77c5-114">**XMLValidator**に対応するオブジェクト モデル内のクラス、 **XML validator**パイプライン コンポーネント、という名前のパブリック プロパティを持つ**RecoverableInterchangeProcessing**を取得または設定モード プログラムで使用することできます。</span><span class="sxs-lookup"><span data-stu-id="b77c5-114">The **XMLValidator** class in the object model, which corresponds to the **XML validator** pipeline component, has a public property named **RecoverableInterchangeProcessing** that you can use to get/set the mode programmatically.</span></span> <span data-ttu-id="b77c5-115">ドキュメントを参照して[Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx)クラスの詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="b77c5-115">See documentation for [Microsoft.BizTalk.Component.XmlValidator](http://msdn.microsoft.com/library/microsoft.biztalk.component.xmlvalidator.aspx) class for more information.</span></span>  
  
   <span data-ttu-id="b77c5-116">正常に検証メッセージがある、送信元パーティを親のインターチェンジが到着する受信ポート用に構成されたパーティに応じて確認します。</span><span class="sxs-lookup"><span data-stu-id="b77c5-116">Messages that are successfully validated have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="b77c5-117">インターチェンジから抽出されたメッセージのパーティの解決に失敗した場合は、インターチェンジ全体に対する失敗したパーティの解決が考慮します。</span><span class="sxs-lookup"><span data-stu-id="b77c5-117">If party resolution for any message extracted from the interchange fails, then the party resolution is considered to have failed for the entire interchange.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b77c5-118">参照</span><span class="sxs-lookup"><span data-stu-id="b77c5-118">See Also</span></span>  
 [<span data-ttu-id="b77c5-119">XML 検証パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b77c5-119">How to Configure the XML Validator Pipeline Component</span></span>](../core/how-to-configure-the-xml-validator-pipeline-component.md)