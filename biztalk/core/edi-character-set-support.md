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
# <a name="edi-character-set-support"></a>EDI 文字セットのサポート
このトピックでは、文字セットが BizTalk Server の EDI 機能でサポートされていることを示します。  
  
|EDI エンコード|サポートされている文字セット|  
|------------------|------------------------------|  
|X12 (HIPAA を含む)|X12-基本文字セット (ASCII のサブセット)|  
|-|X12-拡張文字セット (ASCII のサブセットも ISO8859 1 文字含まれています)|  
|-|UTF8 または UNICODE|  
|EDIFACT|UNOA|  
|-|UNOB|  
|-|UNOC-ISO 8859-1:情報処理 - Part 1:ラテン語アルファベット No. 1|  
|-|KECA - KS_C_5601 1987 (Windows 949 コード ページ)|  
|-|UNOX (ISO2022 – JP)|  
|-|Unoy-utf 8 でエンコードされたデータ**に注意してください。** UNOD UNOK の文字からは、UTF8 でエンコードされたデータはサポートされてもそのサポートを設定します。|  
  
## <a name="setting-the-edi-character-set"></a>EDI 文字セットの設定  
 X12 エンコード インターチェンジの文字、CharacterSet パイプライン プロパティを設定して、パイプラインのセットを設定できます。 詳細については、次を参照してください。 [EDI パイプライン プロパティを設定する](../core/configuring-edi-pipeline-properties.md)します。  
  
> [!NOTE]
>  X12 EDI のプロパティ ダイアログ ボックスは、コントロールは値の検証にのみ使用されますが、BizTalk Server 管理コンソールで、ボックスの x12 インターチェンジのエンベロープの生成 ページで、EDI プロパティに入力した X12 文字セット コントロールがあります。プロパティ ダイアログ ボックス。  
  
 EDIFACT エンコード インターチェンジの場合、文字の UNB セグメントの定義のプロパティ ページでインターチェンジの受信者としてのパーティの UNB1.1 パーティ プロパティを設定して、パーティの設定を設定できます。 受信したインターチェンジで使用するエンコーディングは、インターチェンジのヘッダーにある UNB1.1 フィールドの値によって決まります。 詳細については、次を参照してください。[エンベロープの構成 (EDIFACT トランザクション セットの設定)](../core/configuring-envelopes-edifact-transaction-set-settings.md)します。  
  
## <a name="see-also"></a>参照  
 [EDI パイプラインのプロパティを構成します。](../core/configuring-edi-pipeline-properties.md)   
 [エンベロープの構成 (EDIFACT トランザクション セットの設定)](../core/configuring-envelopes-edifact-transaction-set-settings.md)