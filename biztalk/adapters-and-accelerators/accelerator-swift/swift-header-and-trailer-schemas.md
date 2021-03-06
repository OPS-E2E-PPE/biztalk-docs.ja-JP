---
title: SWIFT ヘッダーおよびトレーラ スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailer schemas
- schemas, headers
- schemas, trailers
- header schemas
ms.assetid: 82cd33d4-6bbb-4124-9506-fd35b5dca8a4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2299ec3a45968cd0aaae2094ec892d03c70972f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529764"
---
# <a name="swift-header-and-trailer-schemas"></a>SWIFT ヘッダーおよびトレーラー スキーマ
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT ヘッダーおよびトレーラのスキーマを提供します。 A4SWIFT は、これらのさまざまな FIN メッセージのインターチェンジのスキーマに既に組み込みます。 カスタム SWIFT FIN 書式スタイル メッセージの種類 (たとえば、N98 メッセージ) を作成する場合は、独自の形式に、ヘッダーとトレーラーのスキーマを組み込むことができます。  
  
 SWIFT ヘッダー スキーマ (SWIFT Header.xsd) には、次の形式が含まれています。  
  
- 基本的なヘッダー  
  
- アプリケーション用のヘッダー (入力または出力の選択)  
  
- ユーザー ヘッダー  
  
- テキスト ブロックの先頭の区切り文字  
  
  基本的なヘッダーには、メッセージのソースに関する情報が含まれています。 アプリケーションのヘッダーには、メッセージの種類およびメッセージの転送先に関する情報が含まれています。 受信パイプラインで SWIFT 逆アセンブラーがメッセージの種類の解像度は、適切なアプリケーションのヘッダー内のフィールドの内容に基づいています。 ユーザー ヘッダーは、省略可能な特別な処理命令が含まれています。  
  
> [!NOTE]
>  いくつかのメッセージの種類には、フィールド 119 ユーザー ヘッダーの内容に基づいて変数の形式があります。 これらは、A4SWIFT で「二重メッセージ型」です。 A4SWIFT 逆アセンブラーでは、119 フィールドの内容と組み合わせてアプリケーション ヘッダー メッセージの種類を使用して、メッセージ インスタンスの適切なスキーマを選択します。  
  
 *SWIFT ユーザー向けハンドブック*、これらのヘッダーはすべて、FIN サービスの SWIFT ドキュメントの一部であるについて説明します。  
  
 テキスト ブロックの先頭が"{4:"後にキャリッジ リターンとライン フィードします。 テキスト ブロックの先頭が必要です。  
  
 SWIFT のみを格納しているインターチェンジの処理 (解析と検証) に対応するためにブロック 4、インターチェンジのスキーマ内のすべてのヘッダーとトレーラーのブロックは省略可能としてマークされます。 これは、基本的なヘッダー ブロック 1 と 2 アプリケーション ヘッダー ブロックは必須、SWIFT FIN 仕様から逸脱します。 これにより、ヘッダーを必要としないメッセージを処理するインターチェンジのスキーマを使用することができます。 たとえば、FileAct を通じて受信するメッセージを受け取る場合、バッチ ヘッダーは共通のメッセージ型と同様に、メッセージのソースを含めることができます。  
  
 ランタイム スキーマ DLL には、ヘッダー スキーマも含まれています。 A4SWIFT インストール環境では、ランタイム スキーマ DLL および A4SWIFT プロパティ スキーマを展開します。 処理のため、独自のヘッダーを使用する必要がある場合と定義に、カスタム ヘッダー スキーマを展開し、メッセージ解決のための適切なプロパティを昇格させます。 これを行う場合は、新しいヘッダーを SWIFT 逆アセンブラー (逆アセンブラー) を指定する必要があります。 カスタム ヘッダー スキーマは、その A4SWIFT のインストールが実行時のスキーマ DLL で展開 SWIFT ヘッダー スキーマと同じドキュメントの種類をいないが必要です。 スキーマの名前空間またはルート ノード名、またはその両方を変更してください。  
  
 SWIFT トレーラー スキーマ (**SWIFT Trailer.xsd**)、次の形式が含まれています。  
  
- テキスト ブロックの末尾の区切り記号  
  
- ユーザー トレーラー (ユーザーおよびシステム情報)  
  
- システム トレーラー  
  
  テキスト ブロックの終了区切り記号は、「-}」です。 トレーラーのブロックが始まる"{5:"です。 トレーラーのブロックの内容には、ユーザー情報 (チェックサム、メッセージの認証、独自の認証およびなど) とシステム情報 (遅延メッセージ、メッセージの参照、使用可能な重複するメッセージ、およびなど) の両方が含まれます。 SWIFT によって追加されたトレーラーで区切られた、3 番目のブロックを提供も"{s:"です。 *SWIFT ユーザー向けハンドブック*、"FIN サービス Description"の下で詳しく説明します 5 のブロックの内容。 A4SWIFT が %s のブロックの内容を検証できません。  
  
  実際、FIN インターフェイスまたは SWIFT ネットワークは、トレーラーを追加します。 メッセージにトレーラーが含まれるは、A4SWIFT メッセージを受信するとき、A4SWIFT は、メッセージのトレーラーを実行します。 A4SWIFT では、A4SWIFT はメッセージを受信メッセージにトレーラーがない場合、エラーは発生しません。 として、ヘッダー付き自体には、ブロックをはじめ、トレーラーのエントリはすべて A4SWIFT では省略可能です。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)