---
title: "EDI 文字セットのサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4f4492b-8cbe-48ed-810a-3e73e1cb5996
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c1463d8a06ab5da89306aababfe19362d6308dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-character-set-support"></a><span data-ttu-id="b121d-102">EDI 文字セットのサポート</span><span class="sxs-lookup"><span data-stu-id="b121d-102">EDI Character Set Support</span></span>
<span data-ttu-id="b121d-103">このトピックでは、[!INCLUDE[prague](../includes/prague-md.md)] の EDI 機能でサポートされる文字セットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b121d-103">This topic indicates which character sets are supported in the EDI features of [!INCLUDE[prague](../includes/prague-md.md)].</span></span>  
  
|<span data-ttu-id="b121d-104">EDI エンコード</span><span class="sxs-lookup"><span data-stu-id="b121d-104">EDI Encoding</span></span>|<span data-ttu-id="b121d-105">サポートされている文字セット</span><span class="sxs-lookup"><span data-stu-id="b121d-105">Supported Character Sets</span></span>|  
|------------------|------------------------------|  
|<span data-ttu-id="b121d-106">X12 (HIPAA を含む)</span><span class="sxs-lookup"><span data-stu-id="b121d-106">X12 (including HIPAA)</span></span>|<span data-ttu-id="b121d-107">X12 - 基本文字セット (ASCII のサブセット)</span><span class="sxs-lookup"><span data-stu-id="b121d-107">X12 - Basic character set (subset of ASCII)</span></span>|  
|-|<span data-ttu-id="b121d-108">X12- 拡張文字セット (ASCII のサブセットに加えて ISO8859-1 文字も含まれます)</span><span class="sxs-lookup"><span data-stu-id="b121d-108">X12- Extended character set (subset of ASCII and also includes ISO8859-1 chars)</span></span>|  
|-|<span data-ttu-id="b121d-109">UTF8/UNICODE</span><span class="sxs-lookup"><span data-stu-id="b121d-109">UTF8/UNICODE</span></span>|  
|<span data-ttu-id="b121d-110">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="b121d-110">EDIFACT</span></span>|<span data-ttu-id="b121d-111">UNOA</span><span class="sxs-lookup"><span data-stu-id="b121d-111">UNOA</span></span>|  
|-|<span data-ttu-id="b121d-112">UNOB</span><span class="sxs-lookup"><span data-stu-id="b121d-112">UNOB</span></span>|  
|-|<span data-ttu-id="b121d-113">Unoc-ISO 8859-1: 情報処理 - パート 1: ラテン語アルファベット No.</span><span class="sxs-lookup"><span data-stu-id="b121d-113">UNOC- ISO 8859-1 : Information processing - Part 1: Latin alphabet No.</span></span> <span data-ttu-id="b121d-114">1</span><span class="sxs-lookup"><span data-stu-id="b121d-114">1</span></span>|  
|-|<span data-ttu-id="b121d-115">KECA - KS_C_5601-1987 (Windows 949 コード ページ)</span><span class="sxs-lookup"><span data-stu-id="b121d-115">KECA - KS_C_5601-1987 (Windows 949 Code page)</span></span>|  
|-|<span data-ttu-id="b121d-116">UNOX (ISO2022 - JP)</span><span class="sxs-lookup"><span data-stu-id="b121d-116">UNOX (ISO2022 – JP)</span></span>|  
|-|<span data-ttu-id="b121d-117">Unoy-utf 8 でエンコードされたデータ**注:** UNOD UNOK の文字からの設定をサポートする UTF8 でエンコードされたデータもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b121d-117">UNOY- UTF8 encoded data **Note:**  The UNOD through UNOK character sets that support UTF8 encoded data are also supported.</span></span>|  
  
## <a name="setting-the-edi-character-set"></a><span data-ttu-id="b121d-118">EDI 文字セットの設定</span><span class="sxs-lookup"><span data-stu-id="b121d-118">Setting the EDI Character Set</span></span>  
 <span data-ttu-id="b121d-119">X12 エンコード インターチェンジの場合、CharacterSet パイプライン プロパティを設定することで、パイプラインの文字セットを設定できます。</span><span class="sxs-lookup"><span data-stu-id="b121d-119">For X12 encoded interchanges, you can set the character set for a pipeline by setting the CharacterSet pipeline property.</span></span> <span data-ttu-id="b121d-120">詳細については、次を参照してください。 [EDI パイプライン プロパティを設定する](../core/configuring-edi-pipeline-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="b121d-120">For more information, see [Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b121d-121">BizTalk Server 管理コンソールの [X12 EDI のプロパティ] ダイアログ ボックスにある [X12 インターチェンジのエンベロープの生成] ページには X12 文字セット コントロールがありますが、このコントロールは [EDI のプロパティ] ダイアログ ボックスでプロパティに入力した値の検証にしか使用できません。</span><span class="sxs-lookup"><span data-stu-id="b121d-121">There is an X12 character set control in the X12 Interchange Envelope Generation page of the X12 EDI Properties dialog box in the BizTalk Server Administration console, but that control is only used to validate the values entered for the properties in the EDI Properties dialog box.</span></span>  
  
 <span data-ttu-id="b121d-122">EDIFACT エンコード インターチェンジの場合、パーティの文字セットを設定するには、[UNB セグメントの定義] プロパティ ページで、インターチェンジの受信者であるパーティの UNB1.1 パーティ プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b121d-122">For EDIFACT encoded interchanges, you can set the character set for a party by setting the UNB1.1 party property in the UNB Segment Definition property page for the party as interchange receiver.</span></span> <span data-ttu-id="b121d-123">受信インターチェンジで使用されるエンコードは、インターチェンジのヘッダーにある UNB1.1 フィールドの値によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="b121d-123">The encoding used in an incoming interchange is determined by the value of the UNB1.1 field in the header of the interchange.</span></span> <span data-ttu-id="b121d-124">詳細については、次を参照してください。[エンベロープの構成 (EDIFACT トランザクション セットの設定)](../core/configuring-envelopes-edifact-transaction-set-settings.md)です。</span><span class="sxs-lookup"><span data-stu-id="b121d-124">For more information, see [Configuring Envelopes (EDIFACT-Transaction Set Settings)](../core/configuring-envelopes-edifact-transaction-set-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b121d-125">参照</span><span class="sxs-lookup"><span data-stu-id="b121d-125">See Also</span></span>  
 <span data-ttu-id="b121d-126">[EDI パイプラインのプロパティを構成します。](../core/configuring-edi-pipeline-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b121d-126">[Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md) </span></span>  
 [<span data-ttu-id="b121d-127">エンベロープの構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="b121d-127">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>](../core/configuring-envelopes-edifact-transaction-set-settings.md)