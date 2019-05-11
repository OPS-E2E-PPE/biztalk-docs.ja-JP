---
title: オーケストレーション エンジンの実行時の検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, assemblies
- orchestrations, validating
- validating, orchestration engine
- schemas, validating
- correlations, validating
- validating, schemas
- orchestration engine, runtime validation
- assemblies, validating
- validating, correlations
- validating, orchestrations
- validating
ms.assetid: f6085889-05d6-4eba-a528-9d034c4e4225
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89423ce9b08aee8ed500b599a912f898c7284968
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393969"
---
# <a name="runtime-validation-for-the-orchestration-engine"></a><span data-ttu-id="32ccf-102">オーケストレーション エンジンの実行時の検証</span><span class="sxs-lookup"><span data-stu-id="32ccf-102">Runtime Validation for the Orchestration Engine</span></span>
<span data-ttu-id="32ccf-103">オーケストレーション エンジンを構成して、オーケストレーションのテスト、および構成やデータの潜在的なエラーの診断をサポートする、さまざまな実行時検証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-103">You can configure the orchestration engine to perform various runtime validations that can help you test your orchestration and diagnose configuration or data errors that might arise.</span></span>  
  
 <span data-ttu-id="32ccf-104">これを行うには、BTSNTSvc.exe (通常は BizTalk の展開ディレクトリに格納される) と同じディレクトリにある BTSNTSvc.exe.config という構成ファイルで、フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-104">You can set flags in BTSNTSvc.exe.config, a configuration file that you can create or edit in the same directory as BTSNTSvc.exe (normally in the BizTalk deployment directory).</span></span> <span data-ttu-id="32ccf-105">BTSNTSvc.exe.config ファイルには次のフラグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-105">You can set the following flags in the BTSNTSvc.exe.config file:</span></span>  
  
- <span data-ttu-id="32ccf-106">設定した場合、 **ValidateAssemblies**フラグを`True`エンジンが、オーケストレーションのおよびエラーのスロー時に即時依存のアセンブリによって参照されるすべてのアセンブリをロードしようとしています。Microsoft.XLANGs.Core.AssemblyValidationException します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-106">If you set the **ValidateAssemblies** flag to `True`, the engine tries to load all assemblies referenced by immediate dependent assemblies of an orchestration and upon failure throws Microsoft.XLANGs.Core.AssemblyValidationException.</span></span>  
  
- <span data-ttu-id="32ccf-107">設定した場合、 **ValidateSchemas**フラグを`True`エンジンは、メッセージ部分の型を表すすべてのスキーマの検証には System.Xml.XmlValidatingReader が使用し、障害発生時に System.Xml.XmlException をスローします。</span><span class="sxs-lookup"><span data-stu-id="32ccf-107">If you set the **ValidateSchemas** flag to `True`, the engine uses System.Xml.XmlValidatingReader to validate every schema representing a message part type and upon failure throws System.Xml.XmlException.</span></span>  
  
- <span data-ttu-id="32ccf-108">設定した場合、 **ValidateCorrelations**フラグを`True`エンジンは、受信コンボイのいずれかに一致する関連付けプロパティの値が同じであるし、障害発生時にスローしますすべてのメッセージをコンボイを同時に確認します。発生すると Microsoft.XLANGs.Core.CorrelationValidationException します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-108">If you set the **ValidateCorrelations** flag to `True`, the engine verifies that in a parallel convoy all messages that match one of the convoy receives have the same correlation property values and upon failure throws Microsoft.XLANGs.Core.CorrelationValidationException.</span></span>  
  
- <span data-ttu-id="32ccf-109">設定した場合、 **ExtendedLogging**フラグを`True`エンジンは、昇格させたプロパティを公開に失敗したメッセージをスローする Microsoft.XLANGs.BaseTypes.PublishMessageException の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-109">If you set the **ExtendedLogging** flag to `True`, the engine displays the promoted properties in the information for Microsoft.XLANGs.BaseTypes.PublishMessageException for the message that failed to publish.</span></span>  
  
  <span data-ttu-id="32ccf-110">フラグを構成ファイルから完全に削除すれば、検証を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-110">If you want to disable a validation, remove the flag entirely from the configuration file.</span></span> <span data-ttu-id="32ccf-111">すべての検証が有効化されている場合は、アセンブリ、スキーマ、および関連付けの検証がオーケストレーション エンジンによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-111">When all validations are on, the engine will validate assemblies, schemas, and correlation.</span></span> <span data-ttu-id="32ccf-112">詳細と BTSNTSvc.exe.config の例については、次を参照してください。[オーケストレーション エンジンの構成](../core/orchestration-engine-configuration.md)します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-112">For more information and examples of BTSNTSvc.exe.config, see [Orchestration Engine Configuration](../core/orchestration-engine-configuration.md).</span></span>  
  
## <a name="validate-assemblies"></a><span data-ttu-id="32ccf-113">アセンブリを検証します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-113">Validate Assemblies</span></span>  
 <span data-ttu-id="32ccf-114">オーケストレーション エンジンでは、オーケストレーションによって参照され、かつアクセスの可能なすべてのアセンブリが検証されます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-114">The orchestration engine will verify that any assemblies referenced by the orchestration are available.</span></span> <span data-ttu-id="32ccf-115">検証に合格するためには、オーケストレーションの最初のインスタンスがアクティブ化されるときに、すべての参照アセンブリがグローバル アセンブリ キャッシュ (GAC) に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32ccf-115">For the validation to succeed, all referenced assemblies must be in the Global Assembly Cache (GAC) when the first instance of the orchestration is activated.</span></span> <span data-ttu-id="32ccf-116">検証に失敗すると、アプリケーション ログにエラーが記録され、オーケストレーションが中断されます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-116">If the validation fails, an error will be logged to the application log and the orchestration will be suspended.</span></span>  
  
## <a name="validate-schemas"></a><span data-ttu-id="32ccf-117">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="32ccf-117">Validate Schemas</span></span>  
 <span data-ttu-id="32ccf-118">オーケストレーション エンジンでは、XSD 要素が割り当てられている場合、その要素のデータがスキーマと照合され、検証されます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-118">Any time an XSD part is assigned, the orchestration engine will validate the part's data against its schema.</span></span> <span data-ttu-id="32ccf-119">検証に失敗すると、アプリケーション ログにエラーが記録され、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="32ccf-119">If the validation fails, the error will be logged to the application log and an exception will be thrown.</span></span>  
  
## <a name="validate-correlation"></a><span data-ttu-id="32ccf-120">関連付けの検証</span><span class="sxs-lookup"><span data-stu-id="32ccf-120">Validate Correlation</span></span>  
 <span data-ttu-id="32ccf-121">オーケストレーション エンジンでは、特定のオーケストレーション インスタンスとの関連付けに指定されたプロパティの値が、そのオーケストレーション インスタンスから送信されるすべてのメッセージに反映されているかを検証します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-121">The orchestration engine will confirm that the property values that are specified for correlation with a given instance of an orchestration are reflected in any messages that are sent from that orchestration instance.</span></span> <span data-ttu-id="32ccf-122">場合**validateCorrelation**が設定された場合、エンジンを想定しています、送信されたメッセージには、正しい関連付けの値が含まれています。 チェックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="32ccf-122">If **validateCorrelation** is not set, the engine will assume that the sent message contains the correct correlation values, and no check will be performed.</span></span>  
  
 <span data-ttu-id="32ccf-123">関連付けの検証に失敗した場合、エンジンはエラーをアプリケーション ログに記録し、型の例外をスロー **CorrelationValidationException**します。</span><span class="sxs-lookup"><span data-stu-id="32ccf-123">If any correlation validation fails, the engine will log an error to the application log and throw an exception of type **CorrelationValidationException**.</span></span>  
  
 <span data-ttu-id="32ccf-124">既定では、 **validateCorrelation**が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="32ccf-124">By default, **validateCorrelation** is not set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ccf-125">参照</span><span class="sxs-lookup"><span data-stu-id="32ccf-125">See Also</span></span>  
 <span data-ttu-id="32ccf-126">[オーケストレーションのデバッグ](../core/debugging-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="32ccf-126">[Debugging Orchestrations](../core/debugging-orchestrations.md) </span></span>  
 [<span data-ttu-id="32ccf-127">オーケストレーション エンジンの構成</span><span class="sxs-lookup"><span data-stu-id="32ccf-127">Orchestration Engine Configuration</span></span>](../core/orchestration-engine-configuration.md)