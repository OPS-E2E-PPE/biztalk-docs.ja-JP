---
title: EDI のサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d4f50a9-fc55-400c-a63c-40b697425fea
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04cd9c14b9c3663bdf332155cc9824e1681ca7a6
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710297"
---
# <a name="edi-support-in-biztalk-server"></a>BizTalk Server における EDI のサポート
EDI は BizTalk Server に組み込まれて、オプションのコンポーネントをインストールして、BizTalk Server を構成する場合。 
  
## <a name="feature-set-comparison-chart"></a>機能セットの比較表  
 次の表は、BizTalk Server の EDI のサポートを示します。
  
|機能|解説|  
|---|---|
|トランザクション セットでの ISA セグメントの変更| トランザクション セット固有のアグリーメントを作成します。|  
|ISA11: 米国またはその他の標準の種類| |  
|[Isa12]: インターチェンジ制御バージョン| |  
|Isa 13: インターチェンジ制御番号が (番号の増分)| |  
|Isa 15: Test や Production| |  
|ドキュメント/トランザクション レベルで GS セグメントの変更| |  
|ISA と異なる GS 送信者/受信者 Id の許可| |  
|ISA および GS の送信 Id と異なる受信ドキュメント Id| |  
|ドキュメントの種類を変更する GS01: 機能| |  
|GS04: 日付 (形式を変更する機能)|CCYYMMDD および YYMMDD の形式を選択するための UI が含まれています|  
|GS05: 時刻 (形式を変更する機能)|HHMM、HHMMSS、および HHMMSSdd の形式を選択するための UI が含まれています|  
|GS06: 制御番号を変更します。| |  
|GS07: 機関コード| |  
|GS08: 標準バージョンに配置すること| |  
|実行時に EDI エンベロープを上書きする機能| |  
|カスタム EDI スキーマ| |  
|組織/パーティの設定|別のパーティとアグリーメントを作成します。 テンプレートに基づいてアグリーメントを作成もできます。|  
|EDI ドキュメントのドキュメント定義を介したルーティング| |  
|取引先への自動 997|ビジネス プロファイルに固有の構成|  
|信頼性の高いメッセージング 997 経由で送信 EDI| |  
|EDIFACT のサポート|ISO 9735 v4.1 d05 D93 をサポートしています|  
|X12 サポートします。|2040 に 5030|  
|HIPAA サポート| Microsoft BizTalk Accelerator for HIPAA (BTAHIPAA) のネイティブ EDI 機能の一部として|  
|列挙子/コードリストの削除|Visual Studio/biztalk エディターを使用して|  
|AS2 の送信/受信| AS2 は複数ファイルの添付ファイルのサポート、ファイル名保持のサポートと相互運用性です。|  
|AS2 ファイル名の保持| |  
|AS2 の信頼できるメッセージング| |  
|送信バッチ処理が (単一のトランザクションで複数の種類のトランザクションをまとめる)|各ビジネス プロファイルについて複数のバッチ構成をサポートしています|  
|受信バッチ処理、– インターチェンジ XML ("バッチ化された"受信インターチェンジを保存) またはトランザクション セット XML 構成オプション|受信のバッチ解除、つまり、個別のトランザクション セット Xml にインターチェンジの分割もサポートします。|  
|インターチェンジおよびトランザクション セットの生成と検証 Visual Studio でデザイン時に| |  
|TA1 (技術確認) の生成と調整| |  
|省略可能な EDI および XSD 検証フラグ| |  
|GS レベルでのドキュメントの形式と定義| |  
  
## <a name="see-also"></a>参照  
 [EDI 標準のサポート](../core/edi-standards-support.md)   
 [EDI ドキュメント スキーマのサポート](../core/edi-document-schema-support.md)   
 [EDI 文字セットのサポート](../core/edi-character-set-support.md)