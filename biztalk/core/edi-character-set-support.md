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
# <a name="edi-character-set-support"></a>EDI 文字セットのサポート
このトピックでは、[!INCLUDE[prague](../includes/prague-md.md)] の EDI 機能でサポートされる文字セットについて説明します。  
  
|EDI エンコード|サポートされている文字セット|  
|------------------|------------------------------|  
|X12 (HIPAA を含む)|X12 - 基本文字セット (ASCII のサブセット)|  
|-|X12- 拡張文字セット (ASCII のサブセットに加えて ISO8859-1 文字も含まれます)|  
|-|UTF8/UNICODE|  
|EDIFACT|UNOA|  
|-|UNOB|  
|-|Unoc-ISO 8859-1: 情報処理 - パート 1: ラテン語アルファベット No. 1|  
|-|KECA - KS_C_5601-1987 (Windows 949 コード ページ)|  
|-|UNOX (ISO2022 - JP)|  
|-|Unoy-utf 8 でエンコードされたデータ**注:** UNOD UNOK の文字からの設定をサポートする UTF8 でエンコードされたデータもサポートされています。|  
  
## <a name="setting-the-edi-character-set"></a>EDI 文字セットの設定  
 X12 エンコード インターチェンジの場合、CharacterSet パイプライン プロパティを設定することで、パイプラインの文字セットを設定できます。 詳細については、次を参照してください。 [EDI パイプライン プロパティを設定する](../core/configuring-edi-pipeline-properties.md)です。  
  
> [!NOTE]
>  BizTalk Server 管理コンソールの [X12 EDI のプロパティ] ダイアログ ボックスにある [X12 インターチェンジのエンベロープの生成] ページには X12 文字セット コントロールがありますが、このコントロールは [EDI のプロパティ] ダイアログ ボックスでプロパティに入力した値の検証にしか使用できません。  
  
 EDIFACT エンコード インターチェンジの場合、パーティの文字セットを設定するには、[UNB セグメントの定義] プロパティ ページで、インターチェンジの受信者であるパーティの UNB1.1 パーティ プロパティを設定します。 受信インターチェンジで使用されるエンコードは、インターチェンジのヘッダーにある UNB1.1 フィールドの値によって指定されます。 詳細については、次を参照してください。[エンベロープの構成 (EDIFACT トランザクション セットの設定)](../core/configuring-envelopes-edifact-transaction-set-settings.md)です。  
  
## <a name="see-also"></a>参照  
 [EDI パイプラインのプロパティを構成します。](../core/configuring-edi-pipeline-properties.md)   
 [エンベロープの構成 (EDIFACT トランザクション セットの設定)](../core/configuring-envelopes-edifact-transaction-set-settings.md)