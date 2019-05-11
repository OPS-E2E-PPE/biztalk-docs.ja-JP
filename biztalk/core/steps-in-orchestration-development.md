---
title: オーケストレーションの開発手順 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- designing, orchestrations
- orchestrations, designing
- orchestrations, creating
- creating, orchestrations
- Copy Local property
ms.assetid: 556b1e6c-63a6-4805-a0a5-e555f198fe4e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 062cff21e067f9e7139c849cf0dd73af5eed1748
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244173"
---
# <a name="steps-in-orchestration-development"></a>オーケストレーションの開発手順
オーケストレーションを開発するには、通常、次の基本的な操作を実行します。  
  
-   ビジネス プロセスを表す図形を追加します。  
  
     オーケストレーション デザイナーは、さまざまなアクションまたは他の抽象化を表すために使用できる図形のツールボックスを提供します。 詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)します。  
  
-   メッセージの形式を記述するスキーマを定義します。  
  
     BizTalk エディターでスキーマを定義できます。 詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)します。  
  
-   使用されるメッセージの送信し、受信ポートを定義します。  
  
     メッセージの送信し、受信方法と場所を指定するポートを定義することができます。 詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)します。  
  
-   バインド**送信**と**受信**図形をポート。  
  
     接続することができます、**送信**と**受信**図形をポートと、それらを使用するポート操作を指定します。 詳細については、次を参照してください。[送信図形を構成する方法](../core/how-to-configure-the-send-shape.md)します。 参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)します。  
  
-   割り当てまたはメッセージの間でデータを変換します。  
  
     使用することができます、**メッセージの構築**図形のメッセージの値を割り当てるか、メッセージの変換。 詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)します。  
  
-   書き込みまたはオーケストレーション内で作業する参照として追加したい場合がありますすべてのカスタム コンポーネントを特定します。  
  
> [!NOTE]
>  場合、**ローカル コピー**参照アセンブリのプロパティに設定されて**True**オーケストレーション追加された参照が行われた後に、外部のアセンブリに加えられた変更を取得できませんBizTalk プロジェクトです。  
  
-   定義し、実行中のオーケストレーション内のデータを管理するオーケストレーション変数を割り当てます。  
  
     オーケストレーションの種類 ウィンドウで、変数 フォルダーを使用するには、オーケストレーションの変数を割り当てるし、さまざまな図形で、変数を使用する式を編集するのに BizTalk 式エディタを宣言します。 詳細については、次を参照してください。 [xlang-s データ型](../core/xlang-s-data-types.md)します。  
  
-   完全を期すのためにテストするオーケストレーションをビルドします。  
  
     プロジェクトまたはそれを含んでいるソリューションをコンパイルするときに、オーケストレーションを作成します。 詳細については、次を参照してください。[オーケストレーションのビルド方法](../core/how-to-build-orchestrations.md)します。  
  
## <a name="see-also"></a>参照  
 [ビルドとオーケストレーションの実行](../core/building-and-running-orchestrations.md)   
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーション デザイナーでのオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)