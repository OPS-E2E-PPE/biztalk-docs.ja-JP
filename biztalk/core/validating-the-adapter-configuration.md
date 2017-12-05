---
title: "アダプター構成の検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c03054332e0cd2117c1219afec3dd1aa0a09d6bd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="validating-the-adapter-configuration"></a>アダプターの構成情報の検証
送信ポートと受信場所を追加中にするように求められますでカスタム プロパティを構成する、  **\<** *アダプター名* **\>トランスポートのプロパティ**  ダイアログ ボックス。 AdapterHarness プロジェクトの XSD スキーマ ファイルで、これらのプロパティが定義されています。  
  
 構成スキーマの検証は、以下の 3 つの部分に分かれています。  
  
1.  保存された構成を表示するときに、アダプター フレームワークは、保存された XML ドキュメントをスキーマに基づいて検証してからプロパティ ページに読み込みます。 フレームワークは、ドキュメントが有効ではない場合、構成スキーマ定義が変更されているものと見なします。 有効なドキュメントだけがプロパティ ページに読み込まれます。  
  
2.  アダプターが実装されている場合、構成を保存するときに、 **IAdapterConfigValidation**インターフェイス、フレームワーク、XML ドキュメントが構築されたアダプタにプロパティ ページのデータのシリアル化から渡されます。 アダプターは、そのドキュメントを処理します。 エラーがある場合は、フレームワークでキャッチされる例外が生成されて、ユーザーに表示されます。 不足している値または生成される値は、検証中に生成されます。 使用して、\<参照可能な表示 ="false"\>装飾エントリは非表示、プロパティ グリッドで場合でも、XML インスタンスの値が表示されます。  
  
3.  値をデータベースに格納する前に構成を保存すると、フレームワークはもう一度スキーマに基づいて XML ドキュメントを検証します。 これにより、有効なデータだけが維持されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのデザインの問題点](../core/adapter-design-issues.md)