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
ms.openlocfilehash: cc36a885614eac72f70e588fefe4731717322019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279537"
---
# <a name="validating-the-adapter-configuration"></a>アダプター構成の検証
受信場所と送信ポートを追加すると、中に求められますのカスタム プロパティを構成する、 **\<**<em>アダプター名</em> **\>トランスポートのプロパティ**  ダイアログ ボックス。 AdapterHarness プロジェクトの XSD スキーマ ファイルは、これらのプロパティを定義します。  
  
 3 つの部分で構成スキーマの検証が行われます。  
  
1.  保存された構成を表示するときに、アダプター フレームワークは、プロパティ ページに、ドキュメントを読み込む前にスキーマの保存された XML ドキュメントを検証します。 フレームワークでは、無効なドキュメントが構成のスキーマ定義の変更を示すことを前提としています。 有効なドキュメントだけが、プロパティ ページに読み込まれます。  
  
2.  アダプターが実装されている場合、構成を保存するときに、 **IAdapterConfigValidation**インターフェイス、フレームワーク、XML ドキュメントが構築されたアダプタにプロパティ ページのデータをシリアル化から渡されます。 アダプターは、ドキュメントを処理します。 エラーは、フレームワークでキャッチして、ユーザーに表示される例外を生成する必要があります。 検証中に、不足しているまたは生成された値を生成する必要があります。 使用して、\<ブラウズ show ="false"\>装飾が XML インスタンスに値が表示されますが、プロパティ グリッド内のエントリを表示を抑制します。  
  
3.  値をデータベースに配置する前に、構成を保存するときに、フレームワークはもう一度スキーマに対して XML ドキュメントを検証します。 これにより、唯一の有効なデータを保持します。  
  
## <a name="see-also"></a>参照  
 [アダプターのデザインの問題点](../core/adapter-design-issues.md)