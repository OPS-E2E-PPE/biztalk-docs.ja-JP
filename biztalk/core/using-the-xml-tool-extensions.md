---
title: XML ツール拡張機能を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5613bf15-6c0a-4a82-b200-24d0801d7ece
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8628ffdbbb2844c7ce8afff3dfe903d0723449
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992493"
---
# <a name="using-the-xml-tool-extensions"></a>XML ツール拡張の使用
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の XML ツール拡張を使用すると、スキーマ、マップ、およびメッセージ インスタンスに対してタスクを実行できます。 これらの拡張は、デザイン時に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 環境で使用します。 実行できるタスクは次のとおりです。  
  
- **スキーマの検証**です。 この操作は、EDI ルールに基づいて、EDI スキーマを検証します。 詳細については、次を参照してください。[スキーマ (EDI) の検証](../core/validating-a-schema-edi.md)です。  
  
- **メッセージ インスタンスの検証**です。 この操作では、単一のトランザクション セット (インターチェンジ ヘッダーとグループ ヘッダーを含まない)、または複数のトランザクション セットを含む完全なバッチ化されたインターチェンジ (インターチェンジ ヘッダーとグループ ヘッダーを含む) を検証します。 バッチ化されていないインターチェンジを検証するには、インターチェンジ ヘッダーとグループ ヘッダーをインスタンスから削除する必要があります。 詳細については、次を参照してください。[検証 (EDI) インスタンス](../core/validating-an-instance-edi.md)します。  
  
- **メッセージ インスタンスを生成する**します。 この操作では、完全なバッチ化されたインターチェンジ、またはインターチェンジ ヘッダーとグループ ヘッダーを含まないトランザクション セットを生成します。 インスタンスの生成に使用する区切り記号や識別子などの形式を指定する必要があります。 詳細については、次を参照してください。 [(EDI) インスタンスを生成する](../core/generating-an-instance-edi.md)します。  
  
- **マップのテスト**します。 この操作では、処理対象ドキュメントとマップに基づき、架空のデータを使用した出力ドキュメントを生成します。 詳細については、次を参照してください。[マップのテスト](../core/testing-a-map.md)します。  
  
- **マップの検証**です。 検証を行うと、マップの基になる XSLT を含むファイルと、拡張オブジェクトを含むファイルが生成されます。 詳細については、次を参照してください。[マップ (EDI) の検証](../core/validating-a-map-edi.md)です。  
  
  BizTalk Server では、これらの拡張機能は、EDI スキーマ、マップ、およびメッセージ インスタンスで動作します。 これらの拡張により、複雑な EDI のスキーマ、マップ、およびインターチェンジを、より効果的に処理できます。  
  
  XML ツール拡張は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のセットアップ プログラムにより既定で有効化されます。 ソリューション エクスプ ローラーの Visual Studio で、スキーマをダブルクリックする場合、**スキーマ エディター拡張機能**スキーマのプロパティに設定されて**EDI スキーマ エディタ拡張機能**します。 この設定は、XML ツール拡張を機能させるために必要です。 EDI 拡張機能を選択したままで、他のスキーマ エディター拡張機能を選択することもできます。  
  
## <a name="see-also"></a>参照  
 [インスタンスの生成 (EDI)](../core/generating-an-instance-edi.md)   
 [インスタンスの検証 (EDI)](../core/validating-an-instance-edi.md)   
 [スキーマの検証 (EDI)](../core/validating-a-schema-edi.md)   
 [マップのテスト](../core/testing-a-map.md)   
 [マップの検証 (EDI)](../core/validating-a-map-edi.md)