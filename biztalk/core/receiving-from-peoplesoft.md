---
title: "PeopleSoft から受信 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca87df1875f648abe2a986fb0d94b16865ee72f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="receiving-from-peoplesoft"></a>PeopleSoft からの受信
Microsoft Adapter for PeopleSoft Enterprise は送信アダプターです。 アダプターでは送信請求 - 応答をサポートしているため、クエリを送信し、応答を受け取ることができます。 ただし、データを PeopleSoft からのみ受信する場合は、さらに 2 つの手順が必要です。  
  
1.  名前空間の設定パイプライン コンポーネントを使用してカスタム受信パイプラインを作成します。  
  
2.  HTTP アダプターを使用するポートなど、PeopleSoft からアクセスできる受信ポートを作成します。 受信ポートと共にカスタム受信パイプラインを使用します。  
  
## <a name="set-namespace-pipeline-component"></a>Namespace パイプライン コンポーネントを設定します。  
 PeopleSoft から受信されるメッセージには名前空間は含まれていません。 名前空間の設定パイプライン コンポーネントを使用すると、名前空間を受信メッセージに追加できます。  
  
 名前空間の設定パイプライン コンポーネントの既定の場所は C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component です。 Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll コンポーネントを BizTalk によって使用されるパイプライン コンポーネント ディレクトリにコピーする必要があります。 また、コンポーネントをパイプライン デザイナーで使用するため、Visual Studio ツールボックスにコンポーネントを追加する必要もあります。  
  
 コンポーネントをインストールする方法については、次を参照してください。[パイプライン コンポーネントの配置](../core/deploying-pipeline-components.md)です。  
  
 Visual Studio ツールボックスにコンポーネントを追加する方法の詳細については、次を参照してください。[ツールボックスの使用方法](../core/how-to-use-the-toolbox.md)です。  
  
## <a name="configure-the-set-namespace-pipeline-component"></a>設定 Namespace パイプライン コンポーネントを構成します。  
 名前空間の設定パイプライン コンポーネントには、設定可能な 2 つのプロパティがあります。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**既定のターゲット Namespace**|受信メッセージに固定の名前空間を入れます。|  
|**Target Namespace XPath**|XPath で指定された場所から取得された名前空間を受信メッセージから抽出します。 有効な名前空間が見つからない場合、アプリケーション イベント ログに警告が記録されます。指定した場合、既定のターゲットの名前空間が使用されます。|  
  
 両方のプロパティを空にした場合、コンポーネントでは受信メッセージに名前空間を割り当てませんが、アプリケーション イベント ログに警告を書き込みます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications4.md)