---
title: オーケストレーションの開発手順 |Microsoft ドキュメント
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
ms.openlocfilehash: 3fd0a19754871a6e736365e622513b193dcbf06a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277394"
---
# <a name="steps-in-orchestration-development"></a>オーケストレーションの開発手順
オーケストレーションを開発するには、通常、次のような手順を実行します。  
  
-   目的のビジネス プロセスを表す図形を追加します。  
  
     オーケストレーション デザイナーには、各種のアクションやその他の抽象化された概念を表す図形がツールボックスとして用意されています。 詳細については、次を参照してください。[オーケストレーション図形](../core/orchestration-shapes.md)です。  
  
-   メッセージの形式が記述されたスキーマを定義します。  
  
     スキーマは、BizTalk エディターを使用して定義できます。 詳細については、次を参照してください。[の XML メッセージ スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)です。  
  
-   メッセージの送受信に使用するポートを定義します。  
  
     ポートを定義することにより、メッセージの送受信方法と送受信場所を指定できます。 詳細については、次を参照してください。[オーケストレーションで使用するポート](../core/using-ports-in-orchestrations.md)です。  
  
-   バインド**送信**と**受信**図形をポートです。  
  
     接続することができます、**送信**と**受信**図形をポートおよびそれらを使用するポート操作を指定します。 詳細については、次を参照してください。[送信図形を構成する方法](../core/how-to-configure-the-send-shape.md)です。 参照してください[受信図形を構成する方法](../core/how-to-configure-the-receive-shape.md)です。  
  
-   メッセージへのデータの割り当てや、メッセージ間の変換を行います。  
  
     使用することができます、**メッセージの構築**図形のメッセージの値を割り当てるか、メッセージの変換。 詳細については、次を参照してください。[メッセージの構築](../core/constructing-messages.md)です。  
  
-   オーケストレーションで使用するために、作成する必要のあるカスタム コンポーネント、または参照として追加する必要のあるカスタム コンポーネントを明確にしておきます。  
  
> [!NOTE]
>  場合、**ローカル コピー**参照アセンブリのプロパティに設定されて**True**オーケストレーションでは、参照の初期の追加が行われた後に、外部アセンブリに加えられた変更を取得できませんBizTalk プロジェクトです。  
  
-   実行中のオーケストレーションでデータを管理するための変数を定義し、割り当てます。  
  
     オーケストレーションの変数を宣言するには、[オーケストレーションの種類] ウィンドウの [変数] フォルダーを使用します。また、各種図形において変数が使われた式を編集するには、BizTalk 式エディターを使用します。 詳細については、次を参照してください。 [XLANG s データ型](../core/xlang-s-data-types.md)です。  
  
-   オーケストレーションをビルドして、正常に動作するかテストします。  
  
     オーケストレーションをビルドするには、そのオーケストレーションがホストされているプロジェクトまたはソリューションをコンパイルします。 詳細については、次を参照してください。[オーケストレーションのビルド方法](../core/how-to-build-orchestrations.md)です。  
  
## <a name="see-also"></a>参照  
 [ビルドとオーケストレーションの実行](../core/building-and-running-orchestrations.md)   
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーション デザイナーを使用してオーケストレーションの作成](../core/creating-orchestrations-using-orchestration-designer.md)