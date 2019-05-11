---
title: フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], configuring
- pipeline components, Flat File Disassembler
- messages, flat files
ms.assetid: c09996f6-6035-42a3-a75f-4def4ac39a95
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3c28c05b63f2bdbadf99e8eb191f3ed151c130c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386063"
---
# <a name="how-to-configure-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントを構成する方法
フラット ファイル逆アセンブラー パイプライン コンポーネントは、フラット ファイル形式のドキュメントを逆アセンブルし、XML 形式に変換するのに使用されます。  
  
### <a name="to-configure-the-properties-for-the-flat-file-disassembler-pipeline-component"></a>フラット ファイル逆アセンブラー パイプライン コンポーネントのプロパティを構成するには  
  
1.  フラット ファイル逆アセンブラー パイプライン コンポーネントは、受信パイプラインの逆アセンブル ステージにドラッグします。  
  
2.  [プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ドキュメント スキーマ**|フラット ファイルから XML 形式へのメッセージの解析に使用するフラット ファイル ドキュメント スキーマを選択します。 解析するためのフラット ファイル ドキュメント スキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値:None**に注意してください。** このプロパティのスキーマを指定する必要があります。 またはコンパイル時エラーが発生します。|  
    |**ヘッダー スキーマ**|フラット ファイル メッセージのヘッダー部のスキーマを選択します。 フラット ファイル メッセージのヘッダー部のスキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値:なし|  
    |**ヘッダーを保存します。**|このプロパティを設定**True**フラット ファイル メッセージのヘッダーをメッセージ コンテキストに格納する必要がある場合。 ヘッダーの構造とコンテンツを BizTalk Server でメッセージを使用したフローのフラット ファイル メッセージのヘッダーをそのまま有効にします。 フラット ファイル アセンブラー パイプライン コンポーネントにおけるフラット ファイル形式にメッセージをシリアル化するとき、ヘッダーを使用し、できます。<br /><br /> 保存したヘッダーがフラット ファイル アセンブラーでシリアル化されるときに、ヘッダー ドキュメントのデザイン時プロパティでこの情報は実行時に動的に取得できるためにヘッダーのスキーマの名前がないことができます。 これは、保存したヘッダーのメッセージの種類を使用して行われます。<br /><br /> 既定値:**False**|  
    |**トレーラー スキーマ**|フラット ファイル メッセージのトレーラー部のスキーマを選択します。 フラット ファイル メッセージのトレーラー部のスキーマは、BizTalk エディターで作成できます。<br /><br /> 既定値:なし|  
    |**回復可能なインターチェンジ処理**|"False"の場合は、(この場合、含まれるメッセージの失敗、インターチェンジ全体が中断されます) を単位としてインターチェンジ全体が逆アセンブルを示します。<br /><br /> "True"の場合は、インターチェンジ内のメッセージは個別に抽出される逆アセンブラーでメッセージの経路と中断されている他のユーザー メッセージやメッセージの可能性を示します。<br /><br /> 回復可能なインターチェンジ処理の詳細については、次を参照してください。[回復可能なインターチェンジ処理](../core/recoverable-interchange-processing.md)します。|  
    |**ドキュメント構造を検証します。**|このプロパティを設定**True** (ヘッダー、本文、およびトレーラー) のスキーマに準拠しているかどうかを確認するフラット ファイル メッセージのすべての部分を検証する必要がある場合。 設定されているために、このオプションがフラット ファイル逆アセンブラーのパフォーマンスを低下**False**既定。<br /><br /> 既定値:**False**|  
  
## <a name="see-also"></a>参照  
 [フラット ファイル逆アセンブラー パイプライン コンポーネント](../core/flat-file-disassembler-pipeline-component.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [XML とフラット ファイル プロパティ スキーマおよびプロパティ](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-AssemblerDisassembler (BizTalk Server サンプル フォルダー)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)