---
title: パーティの解決パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c5c56dbb5ae5c74bfefca9554d20c3f4f10afc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340772"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a>パーティの解決パイプライン コンポーネントを構成する方法
ユーザーのセキュリティ ID とクライアントの証明書のサブジェクトを BizTalk Server パーティにマップするパーティの解決パイプライン コンポーネントが使用されます。 マッピングは、BizTalk Server にメッセージを送信したパーティの認証を強制に使用されます。 パートナー管理の詳細については、次を参照してください。[アグリーメントを作成する方法](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)します。  
  
> [!NOTE]
>  Windows ユーザーを検証するパーティの解決パイプライン コンポーネントを有効にするには、パーティに WindowsUser エイリアスを追加する必要があります。 詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a>パーティの解決パイプライン コンポーネントのプロパティを構成するには  
  
1.  パーティの解決パイプライン コンポーネントは、受信パイプラインのパーティの解決ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**証明書によるパーティを解決します。**|設定**True**メッセージの送信元パーティから署名証明書の拇印に基づいてパーティを解決する場合。<br /><br /> 既定値:**True**|  
    |**SID によるパーティを解決します。**|設定**True**センダ アカウントのセキュリティ識別子 (SID) に基づいたパーティの解決を有効にする場合。<br /><br /> 両方のプロパティが設定されている場合**True**、**証明書によるパーティを解決するには**プロパティよりも優先、 **SID によるパーティの解決**プロパティ、つまり両方の場合、証明書と SID が使用可能な証明書のサブジェクトが使用されます。 証明書のサブジェクトを使用して、パーティを解決できない場合、コンポーネントにフォールバックすること、 **SID によるパーティの解決**のスタンプは、プロパティ、および既定値 (秒 ~ 1-5-7) **BTS します。SourcePartyID**します。<br /><br /> 既定値:**True**|  
  
> [!NOTE]
>  ユーザー名に基づいて、BizTalk メッセージ キュー アダプタをパーティの解決に使用する場合は、設定**証明書によるパーティを解決するには**に**False**と**SID によるパーティの解決**に**True**します。  
  
## <a name="see-also"></a>参照  
 [パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [カスタム パーティの解決 (BizTalk Server サンプル)](../core/custom-party-resolution-biztalk-server-sample.md)