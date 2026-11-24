# 데모 샘플 이미지 출처 (`docs/assets/demo_images`)

데모(`demo.html`)가 직접 불러오는 **줄여 쓴 컬러 기판 사진 54장**입니다(원본은 `../samples/`). 정답 박스·정상/불량 구분은 `demo.html`의 `SAMPLES`에 들어 있습니다.

| 파일 | 장수 | 출처 | 라이선스 |
|---|---:|---|---|
| `normal_NN_dslr_pcbK.jpg` | 16 | **PCB DSLR Dataset** (TU Wien CVL) — `pcbK/rec1.jpg`를 기판 영역으로 잘라 760×560으로 축소 | **CC BY 4.0** |
| `normal_NN_rf_<이름>.jpg` | 8 | **Roboflow Universe `pcb_component_detection_2` v2** (project2-ccajc) 학습 이미지 — 640px 중앙을 760×560 비율로 잘라 사용(Roboflow 내보내기 시 증강으로 약간 기울어진 이미지 포함) | **CC BY 4.0** |
| `normal_NN_pku_pcbNN.jpg` | 6 | **PKU-Market-PCB** `PCB_USED`(불량을 넣기 전 원본 기판 사진) — 760×560으로 축소 | **미확인** |
| `anomaly_NN_<유형>_pkuNN.jpg` | 24 | **PKU-Market-PCB** 불량 이미지 6종(open · short · mousebite · spur · copper · missing_hole) × 4 — 불량 위치 주변 1400px 창을 760×560으로 축소, 박스는 같은 데이터셋의 Pascal VOC 주석(XML) 좌표 | **미확인** |

## 출처 · 인용
- **PCB-DSLR**: https://zenodo.org/records/3886553 (DOI 10.5281/zenodo.3886553) · https://cvl.tuwien.ac.at/?p=3020 — Christopher Pramerdorfer, Martin Kampel (TU Wien). CC BY 4.0 → **출처 표기 필수**.
- **Roboflow `pcb_component_detection_2`**: https://universe.roboflow.com/project2-ccajc/pcb_component_detection_2 (v2, 2025-04-17) — Roboflow 사용자 제공, **CC BY 4.0** → 출처 표기 필수.
- **PKU-Market-PCB**: 원 배포처 https://robotics.pkusz.edu.cn/resources/dataset/ , 받은 경로 hyper.ai 미러 https://orion.hyper.ai/datasets/33973 — 안내문: "합성(synthetic) PCB 불량 데이터셋". **불량은 실제 사진 위에 인위적으로 합성한 것**이라 "실제 생산 불량"으로 소개하면 안 됨.
- 원본 데이터셋 전체와 다운로드 기록: [`../samples/README.md`](../samples/README.md)

## 변경 내용 (원본 대비)
- 모두 JPG(품질 84)로 줄이거나 잘랐고, 불량 박스를 이미지에 그려 넣지 않았음(박스는 `SAMPLES` 좌표로 화면에서 겹쳐 그림).

## 사용 시 주의
- **PKU-Market-PCB(30장 중 6장 + 불량 24장)는 라이선스가 확인되지 않았습니다.** 공개 저장소·상업 배포 전에 원 배포처(베이징대)에 확인하거나, 확인 전에는 `normal_*_pku_*`, `anomaly_*` 파일과 `SAMPLES`의 `'K'` 항목을 제거하세요(불량 시연 이미지는 대체 필요).
- 데모의 점수 · 정상/불량 판정은 샘플 정답에 맞춘 **시연 값**이며 실제 AI 결과가 아닙니다.