---
title: 動的データの検証を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic data validation
- validating, dynamic data
ms.assetid: 8dac7f74-92a7-447c-97bf-b1f3ce39b614
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0ff37ff260ca11e594a208c125f229e2961c01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967163"
---
# <a name="using-dynamic-data-validation"></a><span data-ttu-id="c8b06-102">動的データ検証を使用します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-102">Using Dynamic Data Validation</span></span>
<span data-ttu-id="c8b06-103">動的データの検証の重要な部分は、メッセージの内容に対して、メッセージの形式とメッセージの内容の検証を含む動的データを検証しています。</span><span class="sxs-lookup"><span data-stu-id="c8b06-103">An important part of dynamic data validation is validating message content against dynamic data, which includes validating the message format and the message content.</span></span> <span data-ttu-id="c8b06-104">MicrosoftBizTalk Server は、XSD ファイルでは、ドキュメント スキーマを定義し、メッセージ形式を検証します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-104">A document schema, which MicrosoftBizTalk Server implements in an XSD file, defines and validates message formats.</span></span> <span data-ttu-id="c8b06-105">ビジネス ルールは、メッセージの内容を定義する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ビジネス ルール エンジン ポリシーを検証します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-105">Business rules define message content, which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] validates through Business Rule Engine policies.</span></span> <span data-ttu-id="c8b06-106">コンテンツの検証には、メッセージ インスタンス内のデータが、相対的な頻度で変わる可能性のあるデータと一致することの確認を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c8b06-106">Content validation can include confirmation that data in the message instance matches data that may change with relative frequency.</span></span> <span data-ttu-id="c8b06-107">Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のコードを再コンパイルやサービスをシャット ダウンすることがなく、運用環境では、このデータを更新できるように、動的な方法でこの種類の検証を実装します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-107">Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] implements this type of validation in a dynamic manner, so that you can update this data in a production environment, without having to recompile code or shut down services.</span></span>  
  
## <a name="validate-and-expose-data"></a><span data-ttu-id="c8b06-108">検証し、データの公開</span><span class="sxs-lookup"><span data-stu-id="c8b06-108">Validate and Expose Data</span></span>  
 <span data-ttu-id="c8b06-109">動的データ検証 (DDV) を実行するのには、2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="c8b06-109">There are two steps in performing Dynamic Data Validation (DDV):</span></span>  
  
- <span data-ttu-id="c8b06-110">データを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-110">Expose the data.</span></span>  
  
- <span data-ttu-id="c8b06-111">そのデータを使用して検証規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-111">Apply validation rules using that data.</span></span>  
  
  <span data-ttu-id="c8b06-112">DDV は、保存、公開すると、動的なデータをキャッシュ用の次のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-112">DDV provides the following support for storing, exposing, and caching dynamic data:</span></span>  
  
- <span data-ttu-id="c8b06-113">ビジネス ルール エンジンまたはメッセージのクラスは、検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-113">The Business Rule Engine or Message Class performs validation.</span></span>  
  
- <span data-ttu-id="c8b06-114">ビジネス ルール エンジンは、データベース テーブルの列のボキャブラリを使用してデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-114">The Business Rule Engine exposes data through the Database table column vocabulary.</span></span> <span data-ttu-id="c8b06-115">ビジネス ルール エンジンは、パイプラインまたはオーケストレーションから実行している規則セットを実装することによって、メッセージに対してこの動的なデータを検証します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-115">The Business Rule Engine validates this dynamic data against messages by implementing a rule set that runs from a pipeline or orchestration.</span></span>  
  
- <span data-ttu-id="c8b06-116">既存の SQL インターフェイスなど、SQL Enterprise Manager、クエリ アナライザーでは、デザイン時にパッシブは動的なデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-116">Existing SQL interfaces, such as SQL Enterprise Manager and Query Analyzer, expose dynamic data that is passive at design time.</span></span>  
  
- <span data-ttu-id="c8b06-117">ビジネス ルール エンジン データベース テーブル列のボキャブラリ定義では、実行時に動的なデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-117">The Business Rule Engine database table column vocabulary definition exposes dynamic data at run time.</span></span>  
  
- <span data-ttu-id="c8b06-118">ビジネス ルール エンジンは、実行時に、メッセージ インスタンス データを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-118">The Business Rule Engine exposes message instance data at run time.</span></span>  
  
- <span data-ttu-id="c8b06-119">ビジネス ルール エンジンの XML ドキュメントのボキャブラリの定義は、デザイン時に、メッセージ インスタンス データを公開します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-119">A Business Rules Engine XML document vocabulary definition exposes message instance data at design time.</span></span>  
  
- <span data-ttu-id="c8b06-120">作成できますルール デザイン時にビジネス ルール作成ツールのユーザー インターフェイスまたは直接でビジネス ルール言語 (BRL) XML テキスト エディターで。</span><span class="sxs-lookup"><span data-stu-id="c8b06-120">You can compose rules at design time in the Business Rule Composer user interface or directly in Business Rules Language (BRL) XML in a text editor.</span></span>  
  
  <span data-ttu-id="c8b06-121">ビジネス ルールとビジネス ルール エンジンの詳細については、「の開発とビジネス ルール」BizTalk Server のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b06-121">For more information about business rules and the Business Rule Engine, see "Developing with Business Rules" in BizTalk Server Help.</span></span>  
  
## <a name="extending-ddv"></a><span data-ttu-id="c8b06-122">DDV を拡張します。</span><span class="sxs-lookup"><span data-stu-id="c8b06-122">Extending DDV</span></span>  
 <span data-ttu-id="c8b06-123">HL7 ベースのクロス フィールド検証やデータ型の検証を変更する場合は、2 つのことを注意してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b06-123">If you change HL7-based cross-field validation or data type validation, you must note two things:</span></span>  
  
-   <span data-ttu-id="c8b06-124">既存のルールを変更する場合は、再デプロイする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8b06-124">If you modify an existing rule, you do not need to redeploy.</span></span>  
  
-   <span data-ttu-id="c8b06-125">、作成またはパイプライン コンポーネントに影響を与える新しいルールを削除するがコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b06-125">If you create or delete a new rule that a pipeline component affects, then you must recompile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b06-126">参照</span><span class="sxs-lookup"><span data-stu-id="c8b06-126">See Also</span></span>  
 <span data-ttu-id="c8b06-127">[プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span><span class="sxs-lookup"><span data-stu-id="c8b06-127">[Programming Guide](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md) </span></span>  
 [<span data-ttu-id="c8b06-128">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="c8b06-128">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)