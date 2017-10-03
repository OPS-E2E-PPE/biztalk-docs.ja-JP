---
title: "パーティの解決パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c78792cd7c61ed1297954625fbd7da5aedfa04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a>パーティの解決パイプライン コンポーネントを構成する方法
パーティの解決パイプライン コンポーネントは、クライアントのユーザー セキュリティ ID および証明書のサブジェクトを BizTalk Server パーティにマップするために使用されます。 マッピングを使用して、BizTalk Server にメッセージを送信したパーティの認証を行います。 パートナー管理の詳細については、次を参照してください。[アグリーメントを作成する方法](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)です。  
  
> [!NOTE]
>  パーティの解決パイプライン コンポーネントで Windows ユーザーを検証できるようにするには、パーティに WindowsUser エイリアスを追加する必要があります。 詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a>パーティの解決パイプライン コンポーネントのプロパティを構成するには  
  
1.  パーティの解決パイプライン コンポーネントを、受信パイプラインのパーティの解決ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**証明書によるパーティを解決します。**|設定**True**メッセージの受信場所からパーティから署名証明書の拇印に基づいてパーティの解決を有効にする場合。<br /><br /> 既定値:**は True。**|  
    |**SID によるパーティを解決します。**|設定**True**センダ アカウントのセキュリティ識別子 (SID) に基づいたパーティの解決を有効にする場合。<br /><br /> 両方のプロパティが設定されている場合**True**、**証明書によるパーティを解決するには**プロパティよりも優先、 **SID によるパーティの解決**を場合は、両方を意味するプロパティ、証明書と SID が使用可能な証明書のサブジェクトが使用されます。 証明書のサブジェクトを使用して、パーティを解決できない場合、コンポーネントにフォールバックすること、 **SID によるパーティの解決**のスタンプは、プロパティ、および既定値 (s-1-5 ~ 7) **BTS です。SourcePartyID**です。<br /><br /> 既定値:**は True。**|  
  
> [!NOTE]
>  ユーザー名に基づいて、BizTalk メッセージ キュー アダプタと、パーティの解決を使用する場合、設定**証明書によるパーティを解決するには**に**False**と**SID によるパーティの解決**に**True**です。  
  
## <a name="see-also"></a>参照  
 [パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [カスタム パーティの解決 (BizTalk Server サンプル)](../core/custom-party-resolution-biztalk-server-sample.md)