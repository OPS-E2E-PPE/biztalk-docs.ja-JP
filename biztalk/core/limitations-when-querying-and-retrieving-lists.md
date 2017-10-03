---
title: "クエリを実行して、一覧の取得時の制限事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, querying limitations
- querying, limitations [JD Edwards OneWorld adapters]
ms.assetid: 1b6f5d2a-d1e2-4c78-8f4a-f00d10f008b9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2e0f813a793aa05756ef52925081375203f2f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-when-querying-and-retrieving-lists"></a>リストのクエリと取得時の制限事項
JD Edwards OneWorld の通信アーキテクチャは、単一メッセージ、単一応答のアーキテクチャです。 メッセージのリストまたは配列を返すことはできません。 基になるコードは C++ であり、C++ では、1 つの構造体へのポインタを指定して呼び出し、その構造体で変更を行って、関数が終了します。  
  
## <a name="querying-and-retrieving-lists"></a>リストのクエリと取得  
 JD Edwards OneWorld のビジネス関数アーキテクチャの制限により、Microsoft BizTalk Adapter for JD Edwards OneWorld を使用して検索条件に基づきレコードのリストをクエリおよび取得することはできません。  
  
 JD Edwards OneWorld では、専用の (複雑な) 内部関数呼び出しを使用して、データベース接続が実現されます。 取得または更新する列のリストを作成し、並べ替えまたは選択用の特別な構造体を作成するために明示的な低レベルの呼び出しが必要とされるため、専用の内部関数呼び出しによって基になるデータベースの関数呼び出しはマスクされます。 API セットは Java (または他の) 接続メソッドでは公開されないため、ビジネス関数を使用してレコードセットを処理することはできません。  
  
 JD Edwards OneWorld ツールセット内で、1 つのレコードまたはレコードセットを処理するビジネス関数を作成することはできますが、JD Edwards OneWorld ツールの外部にある項目のリストにアクセスするのはより困難です。  
  
 この問題を回避するために、クエリに基づいてレコード キーのリストを返すカスタム ビジネス関数を作成できます。 JDENET (JD Edwards OneWorld 内部の専用メッセージング API) では、大規模または無制限の結果セットを管理するためのメッセージ バッファ サイズに制限があるため、リストをセグメント化する必要があります。 リストが完了したことを示すインジケータが返されるまで、クライアント コードはそのビジネス関数の連続呼び出しで反復 (ループ) しなければなりません。  
  
## <a name="controlling-iteration"></a>繰り返しの制御  
 JD Edwards OneWorld ビジネス関数の呼び出しはすべてステートレスであるため、オープン カーソルを保持し、要求に応じて追加の行を返すことができません。 呼び出しごとに、JD Edwards OneWorld XE ビジネス関数に位置情報を渡す必要があります。  
  
 繰り返しを制御するための方法の一覧を次に示します。  
  
-   JD Edwards OneWorld 側で、結果セットを一時ストレージ ファイルに書き込みます。この一時ストレージ ファイルは、連続呼び出しに渡される (ファイル名やジョブ番号などの) ID を、カーソル位置を指定するレコード番号と共に返します。 それぞれの連続呼び出しは、渡されたレコード番号に基づいてリスト内で位置指定されます。  
  
    > [!NOTE]
    >  BizTalk Adapter for JD Edwards OneWorld を経由した呼び出しは負荷分散できますが、最終的には、呼び出し先の資格情報とビジネス関数に基づいて単一のアプリケーション サーバーによって実行されます。 したがって、ある呼び出しによってサーバー上に一時ファイルが作成されると、2 回目以降の呼び出しは同じサーバーで処理されます。 詳細については、『JD Edwards OneWorld CNC Guides』の「Object Configuration Mapping」を参照してください。  
  
-   2 回目以降の呼び出しで (主キーの値などの) 位置情報を返し、そのキーを追加のパラメータとして渡してクエリを再実行できます。 この方法は、BizTalk Adapter for JD Edwards OneWorld のリポジトリ参照コードで使用されます。  
  
    > [!NOTE]
    >  最初の 2 つの方法のうち、主キーの値を使用してクエリを再実行する方法をお勧めします。 この方法の場合、必要になるコードの量が最も少なく、最適化やキャッシュの負荷はデータベースに課せられます。  
  
-   呼び出し元のアプリケーションは、主キーのリスト (相互参照など) を格納できます。 たとえば、カスタマ リレーションシップ マネジメント (CRM) システムによって顧客レコードが作成され、ビジネス関数呼び出しを使用して JD Edwards OneWorld に追加された場合、この顧客レコードを追加するビジネス関数は AN8 フィールド (short アドレス番号) の値を設定し、リターン バッファで可視になります。 この番号は、元の顧客レコードの参照フィールドに書き込まれるか、カスタマイズされた相互参照テーブルに格納されます。  
  
-   JD Edwards OneWorld の大部分のマスタ レコードには、ルックアップ キーまたは代替キーという概念があります。 このキーを使用して、呼び出し元のシステムからのキー情報を格納できます。 ビジネス関数は、JD Edwards OneWorld 側でルックアップを実行できます。 顧客レコードを作成するためにビジネス関数にパラメータが渡されるとき、long キー値が設定されます。  
  
 これらの概念の詳細については、JD Edwards OneWorld ヘルプ システムの「Interoperability」を参照してください。  
  
## <a name="see-also"></a>参照  
 [計画とアーキテクチャ](../core/planning-and-architecture17.md)