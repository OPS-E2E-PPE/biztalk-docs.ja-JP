---
title: パイプライン コンポーネントの開発、プローブ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], probing
- IProbeMessage interface
- pipeline interfaces, IProbeMessage
ms.assetid: c3da467d-5270-4c7f-9c38-ce9989bf1b63
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54da9d0433b0ca416e5c0da797a4d4c8678aab8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389455"
---
# <a name="developing-a-probing-pipeline-component"></a>プローブ パイプライン コンポーネントの開発
任意のパイプライン コンポーネント (全般、アセンブル、または逆アセンブル) を実装できる、`IProbeMessage`インターフェイスの場合はメッセージ プローブ機能をサポートする必要があります。 プローブ コンポーネントがされているパイプライン ステージで使用される**FirstMatch**実行モード。 このモードのステージで、BizTalk メッセージング エンジンには、コンポーネント、コンポーネントのかどうか、メッセージの形式を認識するメッセージの先頭部分が付与されます。 コンポーネントには、形式が認識している場合は、メッセージ全体が処理するためのコンポーネントに付与されます。  
  
 **IProbeMessage**インターフェイスは 1 つのメソッドを公開**プローブ**、使用して、コンポーネントをメッセージの先頭部分を確認します。 戻り値は、このコンポーネントが実行されているかどうかを判断します。 次の手順では、BizTalk メッセージング エンジンが認識を必要とするステージを実行する方法を示しています。  
  
1. ステージにコンポーネントが含まれていない場合は、ステージが実行されないと、メッセージが処理するための後続のステージに渡さします。  
  
2. コンポーネントを実装するかどうかの確認、 **IProbeMessage**インターフェイス。 それ以外の場合は、メッセージング エンジンは、コンポーネントを呼び出します。 ステージ処理が完了し、メッセージは次のステージに渡さします。  
  
3. **プローブ**メソッドが呼び出されます。 戻り値が場合**True**コンポーネントを実行します。 ステージ処理が完了し、メッセージは次のステージに渡さします。  
  
4. メッセージング エンジンは、ステージ内の次のコンポーネントを取得します。 コンポーネントがないが存在し、コンポーネントのいずれも実行されている場合、エラーを生成します。 パイプライン処理が失敗しました。 コンポーネントがないが存在し、少なくとも 1 つのコンポーネントが実行されている場合、処理が行われます。  
  
   ステージに認識が必要としない場合 (たとえば、実行モードは**すべて**)、メッセージング エンジンは、最初のクエリを実行することがなく、コンポーネントを呼び出します、 **IProbeMessage**インターフェイスと呼び出し、**プローブ**メソッド。  
  
## <a name="see-also"></a>参照  
 [全般パイプライン コンポーネントの開発](../core/developing-a-general-pipeline-component.md)   
 [アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)   
 [パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)