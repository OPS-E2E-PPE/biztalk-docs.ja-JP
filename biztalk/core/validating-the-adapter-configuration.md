---
title: アダプター構成の検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7fa3af1fa0116f859f0d3f39f2235be38cbc0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008131"
---
# <a name="validating-the-adapter-configuration"></a>アダプターの構成情報の検証
受信場所と送信ポートを追加すると、中に求められますのカスタム プロパティを構成する、 **\<**<em>アダプター名</em> **\>トランスポートのプロパティ**  ダイアログ ボックス。 AdapterHarness プロジェクトの XSD スキーマ ファイルで、これらのプロパティが定義されています。  
  
 構成スキーマの検証は、以下の 3 つの部分に分かれています。  
  
1.  保存された構成を表示するときに、アダプター フレームワークは、保存された XML ドキュメントをスキーマに基づいて検証してからプロパティ ページに読み込みます。 フレームワークは、ドキュメントが有効ではない場合、構成スキーマ定義が変更されているものと見なします。 有効なドキュメントだけがプロパティ ページに読み込まれます。  
  
2.  アダプターが実装されている場合、構成を保存するときに、 **IAdapterConfigValidation**インターフェイス、フレームワーク、XML ドキュメントが構築されたアダプタにプロパティ ページのデータをシリアル化から渡されます。 アダプターは、そのドキュメントを処理します。 エラーがある場合は、フレームワークでキャッチされる例外が生成されて、ユーザーに表示されます。 不足している値または生成される値は、検証中に生成されます。 使用して、\<ブラウズ show ="false"\>装飾が XML インスタンスに値が表示されますが、プロパティ グリッド内のエントリを表示を抑制します。  
  
3.  値をデータベースに格納する前に構成を保存すると、フレームワークはもう一度スキーマに基づいて XML ドキュメントを検証します。 これにより、有効なデータだけが維持されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのデザインの問題点](../core/adapter-design-issues.md)