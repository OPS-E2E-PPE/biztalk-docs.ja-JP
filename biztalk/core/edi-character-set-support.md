---
title: EDI 文字セットのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f4492b-8cbe-48ed-810a-3e73e1cb5996
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c38e7a8115be79d44e39cb4b1c60ef975219ad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350457"
---
# <a name="edi-character-set-support"></a><span data-ttu-id="bc12c-102">EDI 文字セットのサポート</span><span class="sxs-lookup"><span data-stu-id="bc12c-102">EDI Character Set Support</span></span>
<span data-ttu-id="bc12c-103">このトピックでは、文字セットが BizTalk Server の EDI 機能でサポートされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="bc12c-103">This topic indicates which character sets are supported in the EDI features of BizTalk Server.</span></span>  
  
|<span data-ttu-id="bc12c-104">EDI エンコード</span><span class="sxs-lookup"><span data-stu-id="bc12c-104">EDI Encoding</span></span>|<span data-ttu-id="bc12c-105">サポートされている文字セット</span><span class="sxs-lookup"><span data-stu-id="bc12c-105">Supported Character Sets</span></span>|  
|------------------|------------------------------|  
|<span data-ttu-id="bc12c-106">X12 (HIPAA を含む)</span><span class="sxs-lookup"><span data-stu-id="bc12c-106">X12 (including HIPAA)</span></span>|<span data-ttu-id="bc12c-107">X12-基本文字セット (ASCII のサブセット)</span><span class="sxs-lookup"><span data-stu-id="bc12c-107">X12 - Basic character set (subset of ASCII)</span></span>|  
|-|<span data-ttu-id="bc12c-108">X12-拡張文字セット (ASCII のサブセットも ISO8859 1 文字含まれています)</span><span class="sxs-lookup"><span data-stu-id="bc12c-108">X12- Extended character set (subset of ASCII and also includes ISO8859-1 chars)</span></span>|  
|-|<span data-ttu-id="bc12c-109">UTF8 または UNICODE</span><span class="sxs-lookup"><span data-stu-id="bc12c-109">UTF8/UNICODE</span></span>|  
|<span data-ttu-id="bc12c-110">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="bc12c-110">EDIFACT</span></span>|<span data-ttu-id="bc12c-111">UNOA</span><span class="sxs-lookup"><span data-stu-id="bc12c-111">UNOA</span></span>|  
|-|<span data-ttu-id="bc12c-112">UNOB</span><span class="sxs-lookup"><span data-stu-id="bc12c-112">UNOB</span></span>|  
|-|<span data-ttu-id="bc12c-113">UNOC-ISO 8859-1:情報処理 - Part 1:ラテン語アルファベット No.</span><span class="sxs-lookup"><span data-stu-id="bc12c-113">UNOC- ISO 8859-1 : Information processing - Part 1: Latin alphabet No.</span></span> <span data-ttu-id="bc12c-114">1</span><span class="sxs-lookup"><span data-stu-id="bc12c-114">1</span></span>|  
|-|<span data-ttu-id="bc12c-115">KECA - KS_C_5601 1987 (Windows 949 コード ページ)</span><span class="sxs-lookup"><span data-stu-id="bc12c-115">KECA - KS_C_5601-1987 (Windows 949 Code page)</span></span>|  
|-|<span data-ttu-id="bc12c-116">UNOX (ISO2022 – JP)</span><span class="sxs-lookup"><span data-stu-id="bc12c-116">UNOX (ISO2022 – JP)</span></span>|  
|-|<span data-ttu-id="bc12c-117">Unoy-utf 8 でエンコードされたデータ**に注意してください。** UNOD UNOK の文字からは、UTF8 でエンコードされたデータはサポートされてもそのサポートを設定します。</span><span class="sxs-lookup"><span data-stu-id="bc12c-117">UNOY- UTF8 encoded data **Note:**  The UNOD through UNOK character sets that support UTF8 encoded data are also supported.</span></span>|  
  
## <a name="setting-the-edi-character-set"></a><span data-ttu-id="bc12c-118">EDI 文字セットの設定</span><span class="sxs-lookup"><span data-stu-id="bc12c-118">Setting the EDI Character Set</span></span>  
 <span data-ttu-id="bc12c-119">X12 エンコード インターチェンジの文字、CharacterSet パイプライン プロパティを設定して、パイプラインのセットを設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc12c-119">For X12 encoded interchanges, you can set the character set for a pipeline by setting the CharacterSet pipeline property.</span></span> <span data-ttu-id="bc12c-120">詳細については、次を参照してください。 [EDI パイプライン プロパティを設定する](../core/configuring-edi-pipeline-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc12c-120">For more information, see [Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc12c-121">X12 EDI のプロパティ ダイアログ ボックスは、コントロールは値の検証にのみ使用されますが、BizTalk Server 管理コンソールで、ボックスの x12 インターチェンジのエンベロープの生成 ページで、EDI プロパティに入力した X12 文字セット コントロールがあります。プロパティ ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bc12c-121">There is an X12 character set control in the X12 Interchange Envelope Generation page of the X12 EDI Properties dialog box in the BizTalk Server Administration console, but that control is only used to validate the values entered for the properties in the EDI Properties dialog box.</span></span>  
  
 <span data-ttu-id="bc12c-122">EDIFACT エンコード インターチェンジの場合、文字の UNB セグメントの定義のプロパティ ページでインターチェンジの受信者としてのパーティの UNB1.1 パーティ プロパティを設定して、パーティの設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bc12c-122">For EDIFACT encoded interchanges, you can set the character set for a party by setting the UNB1.1 party property in the UNB Segment Definition property page for the party as interchange receiver.</span></span> <span data-ttu-id="bc12c-123">受信したインターチェンジで使用するエンコーディングは、インターチェンジのヘッダーにある UNB1.1 フィールドの値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="bc12c-123">The encoding used in an incoming interchange is determined by the value of the UNB1.1 field in the header of the interchange.</span></span> <span data-ttu-id="bc12c-124">詳細については、次を参照してください。[エンベロープの構成 (EDIFACT トランザクション セットの設定)](../core/configuring-envelopes-edifact-transaction-set-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc12c-124">For more information, see [Configuring Envelopes (EDIFACT-Transaction Set Settings)](../core/configuring-envelopes-edifact-transaction-set-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc12c-125">参照</span><span class="sxs-lookup"><span data-stu-id="bc12c-125">See Also</span></span>  
 <span data-ttu-id="bc12c-126">[EDI パイプラインのプロパティを構成します。](../core/configuring-edi-pipeline-properties.md) </span><span class="sxs-lookup"><span data-stu-id="bc12c-126">[Configuring EDI Pipeline Properties](../core/configuring-edi-pipeline-properties.md) </span></span>  
 [<span data-ttu-id="bc12c-127">エンベロープの構成 (EDIFACT トランザクション セットの設定)</span><span class="sxs-lookup"><span data-stu-id="bc12c-127">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>](../core/configuring-envelopes-edifact-transaction-set-settings.md)