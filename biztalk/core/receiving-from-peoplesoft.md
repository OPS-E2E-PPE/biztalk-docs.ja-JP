---
title: PeopleSoft からの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3861d885188762b69a08359fbaf9161e02aa5759
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398088"
---
# <a name="receiving-from-peoplesoft"></a>PeopleSoft からの受信
Microsoft Adapter for PeopleSoft Enterprise は、送信アダプターです。 アダプターは、クエリを送信し、応答を受け取るように、送信請求-応答をサポートしています。 ただし、PeopleSoft からデータを受信するだけの場合は、2 つの追加手順を行う必要があります。  
  
1.  Namespace の設定パイプライン コンポーネントを使用してカスタム受信パイプラインを作成します。  
  
2.  受信ポートの作成アクセス可能な PeopleSoft から (HTTP アダプターを使用するポートなど)。 受信ポートでは、カスタム受信パイプラインを使用します。  
  
## <a name="set-namespace-pipeline-component"></a>Namespace パイプライン コンポーネントを設定します。  
 PeopleSoft から受信したメッセージは、名前空間を含めないでください。 Namespace の設定パイプライン コンポーネントでは、受信メッセージに名前空間を追加することができます。  
  
 Namespace の設定パイプライン コンポーネントの既定の場所は C:\Program files \microsoft BizTalk Adapters Enterprise applications \pipeline Component for です。 Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll コンポーネントを BizTalk で使用されるパイプライン コンポーネント ディレクトリにコピーする必要があります。 また、パイプライン デザイナーで使用するには、Visual Studio のツールボックスにコンポーネントを追加する必要があります。  
  
 コンポーネントをインストールする場所については、次を参照してください。[パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)します。  
  
 Visual Studio ツールボックスにコンポーネントを追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)します。  
  
## <a name="configure-the-set-namespace-pipeline-component"></a>セット Namespace パイプライン コンポーネントを構成します。  
 Namespace の設定パイプライン コンポーネントには、2 つのプロパティを設定することがあります。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**既定のターゲット Namespace**|受信メッセージには、固定の名前空間を配置します。|  
|**Target Namespace XPath**|名前空間は、XPath で指定された場所から取得された受信メッセージから抽出します。 有効な名前空間が見つからない場合、アプリケーション イベント ログに警告を記録し、指定されている場合は、ターゲットの既定の Namespace を使用します。|  
  
 両方のプロパティを空白のままにした場合、コンポーネントが受信したメッセージに名前空間を割り当てられませんが、アプリケーション イベント ログに警告を書き込みます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications4.md)